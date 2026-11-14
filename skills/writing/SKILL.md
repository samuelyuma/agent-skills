---
name: writing
description: Write, explain, summarize, and edit human-facing prose so it is clear and easy to follow, in English or Indonesian, including plain-language UI copy and public-service content. Use for chat answers, documents, reports, PR descriptions, commit messages, code comments, microcopy, and requests to humanize or remove AI-sounding wording. Not for agent instruction files or text the user wants kept word for word.
---

# Writing

Make the point easy to understand and act on. This skill controls sentences, not document structure, research, or engineering decisions.

Always read `references/core.md`. Then read only the files that match the task. Paths are relative to this skill.

| Task | Also read |
|---|---|
| Writing or editing in Indonesian | `references/languages/indonesian.md` |
| English cleanup or word choice | `references/languages/english.md` |
| Public-facing Indonesian: notices, guides, forms | `references/public-content.md`, `references/languages/indonesian-plain.md` |
| Public-facing English: notices, guides, forms | `references/public-content.md`, `references/languages/english-plain.md` |
| UI copy, microcopy, product strings | `references/use-cases/ui-copy.md`, `references/public-content.md`, and the matching plain-language file |
| Final quality pass on public content | `references/rasa.md` |
| Chat answers, recommendations, progress updates | `references/use-cases/chat.md` |
| Teaching or explaining a concept | `references/explaining.md` |
| Documents, READMEs, reports | `references/use-cases/documents.md` |
| PR title or description | `references/use-cases/pull-requests.md` |
| Commit message | `references/use-cases/commits.md` |
| Code comments and docstrings | `references/use-cases/comments.md` |
| Cleaning up or rewriting existing text | `references/editing.md` |
| Summarizing | `references/summarizing.md` |
| Humanize, remove AI wording | `references/anti-slop.md` (short list), `references/anti-slop-detail.md` only if the short list is not enough |

Fixed rules:

- Reply in the language of the user's current message. Edits keep the source language unless translation is requested.
- Public-facing copy follows `references/public-content.md`. Inside that scope, sentence case and the no-emphasis rule replace the core defaults. Do not apply them to chat, PRs, commits, or developer documents.
- Shorter must not mean harder to read. Never drop the subject or the connecting words (karena, supaya, sehingga, because, so) to save space.
- Keep every claim, condition, number, unit, negation, and step order. Never add facts, measurements, or checks that were not given.
- Keep code, commands, paths, identifiers, error text, and quotations exactly as written.
- Drafting text does not authorize committing, publishing, or editing files that were not requested.
