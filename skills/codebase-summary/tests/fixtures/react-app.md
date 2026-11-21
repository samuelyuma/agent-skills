# React App Evidence

All names, paths, and code below are invented for isolated evaluation. No application or tests have been run. The server's internal behavior is not supplied.

## README.md

The dashboard lets a user rename a project. The new name appears immediately and is saved to the server.

## src/main.tsx

```tsx
const store = createProjectStore();
root.render(
  <StoreProvider store={store}>
    <ProjectPage />
  </StoreProvider>
);
```

## src/ProjectPage.tsx

```tsx
function ProjectPage() {
  const { project, rename } = useProject();
  const [draft, setDraft] = useState(project.name);
  return (
    <form onSubmit={(e) => { e.preventDefault(); rename(draft); }}>
      <input value={draft} onChange={(e) => setDraft(e.target.value)} />
      <button type="submit">Save</button>
      {project.error && <p role="alert">{project.error}</p>}
    </form>
  );
}
```

## src/useProject.ts

```ts
export function useProject() {
  const store = useStore();
  const project = store.select((s) => s.project);
  async function rename(name: string) {
    const previous = project.name;
    store.update((s) => { s.project.name = name; s.project.error = null; });
    try {
      await api.patch(`/projects/${project.id}`, { name });
    } catch {
      store.update((s) => { s.project.name = previous; s.project.error = "Could not save"; });
    }
  }
  return { project, rename };
}
```

The supplied `api.patch` contract says it rejects on a non-2xx response. The server route, validation rules, and any later refresh of the project from the server are not supplied.

## tests/rename.spec

Unrun expectation: after a rejected request the project name returns to its previous value and an alert is shown. No test result is supplied.
