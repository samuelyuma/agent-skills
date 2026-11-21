# Queued Work Evidence

All names, paths, documentation, and pseudocode below are invented for isolated evaluation. Pseudocode establishes the stated connections only; no framework behavior is implied. No application or tests have been run.

## README.md

The service accepts report jobs and emails their results. It sends the email before replying to a submission.

## app/start.task

```text
store = Store()
dispatch = Dispatcher()
dispatch.bind(SubmitJob, SubmitJobHandler(store))
server.route("POST /jobs", SubmitEndpoint(dispatch))
scheduler.every(30, PollJobs(store, ReportWorker(renderer, mailer)))
server.start()
```

## app/submit.task

```text
SubmitEndpoint.handle(body):
  id = dispatch.send(SubmitJob(body.address, body.filters))
  return Reply(status=202, body={id: id})

Dispatcher.send(command):
  return bindings[type(command)].handle(command)

SubmitJobHandler.handle(command):
  if command.address is empty:
    raise InvalidAddress
  id = new_id()
  store.transaction:
    store.jobs.insert(id, command.filters, status="queued")
    store.pending.insert(id, command.address)
  return id
```

The supplied store contract says leaving a successful transaction block commits both inserts atomically. It says nothing about the queue delivery semantics. Error-to-response mapping is not supplied.

## app/background.task

```text
PollJobs.tick():
  for item in store.pending.available():
    worker.process(item)

ReportWorker.process(item):
  job = store.jobs.get(item.id)
  report = renderer.render(job.filters)
  mailer.send(item.address, report)
  store.jobs.set_status(item.id, "sent")
  store.pending.remove(item.id)
```

The renderer, mailer, scheduler, and pending-store internals are not supplied. No retry, delivery, scheduling-overlap, or crash-recovery guarantees are supplied.

## tests/submit.spec

Unrun expectation: a valid submission returns status 202 and persists one queued job plus one pending item. No test result is supplied.
