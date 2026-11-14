# Agent Skills

Reusable skills for coding agents, maintained by [samuelyuma](https://github.com/samuelyuma).
Each skill includes instructions, supporting references, and evaluation scenarios.

## Install

Install with the [skills CLI](https://github.com/vercel-labs/skills). It requires
Git and a supported Node.js installation.

```sh
npx skills add samuelyuma/agent-skills
```

Choose the skills and agents when prompted. Installation defaults to the current
project. Add `--global` to make the skills available across projects.

To install only the writing skill for Codex:

```sh
npx skills add samuelyuma/agent-skills --skill writing --agent codex
```

To list the available skills without installing them:

```sh
npx skills add samuelyuma/agent-skills --list
```

## Available Skills

- [agent-instructions](skills/agent-instructions/SKILL.md): create and review
  repository or global agent instructions, such as `AGENTS.md`.
- [documentation](skills/documentation/SKILL.md): write and maintain READMEs,
  guides, API specifications, proposals, release notes, and reports.
- [plan](skills/plan/SKILL.md): create and review implementation plans grounded
  in the repository, with decisions and verification steps.
- [research](skills/research/SKILL.md): investigate questions, verify claims,
  and compare options using repository evidence and authoritative sources.
- [writing](skills/writing/SKILL.md): write and edit clear English or Indonesian
  prose for chat, documents, PRs, commits, and code comments.

The skills work individually. References to other skills are optional; installing
all five gives an agent the related workflows as well.

## Local Development

Edit skills under `skills/<name>/`. Each folder contains `SKILL.md` and the
references, assets, or tests it needs. Keep supporting files with their skill so
the installed copy can use them.

From the repository root, verify that the installer discovers the skills:

```sh
npx skills add . --list
```

The `tests/cases.md` and `tests/rubric.md` files inside each skill describe
behavioral evaluation scenarios. Use the relevant cases when changing a skill;
installer discovery alone does not verify an agent's behavior.

## Credits

Public-content guidance in the writing skill includes material adapted from
[orepras](https://github.com/orepras). See [CREDITS.md](CREDITS.md) for
sources, revisions, and permission status.

## License

[MIT](LICENSE).
