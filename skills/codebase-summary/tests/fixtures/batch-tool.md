# Batch Tool Evidence

All names, paths, and pseudocode below are invented for isolated evaluation. No tool execution or test results are supplied. This snapshot has no README.

## tasks.conf

```text
default = tools/collect.task
```

## tools/collect.task

```text
main(input_path, output_path):
  rows = reader.read(input_path)
  result = summarize(rows)
  if result is Empty:
    return Exit(code=2, message="No rows")
  writer.replace(output_path, result)
  return Exit(code=0, message="Written")

summarize(rows):
  if rows is empty:
    return Empty
  totals = group_and_sum(rows, key="category", value="amount")
  return sort_by_category(totals)
```

## tools/wiring.task

```text
reader = DelimitedReader(separator=";")
writer = LocalFileWriter()
```

The task loader connects `tools/wiring.task` bindings to `tools/collect.task` before invoking `main`. Its supplied contract establishes that wiring only. Reader and writer implementations are not supplied; atomic replacement, encoding, and filesystem error handling are unknown.
