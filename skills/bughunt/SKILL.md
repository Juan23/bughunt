---
name: docdiet
description: Machine-global toggle for mandatory, bounded documentation hygiene during normal work.
---

# $docdiet

`docdiet` is a machine-global toggle stored at `~/.codex/.docdiet-off`.
It is ON by default:

- `$docdiet on` removes the sentinel.
- `$docdiet off` creates it.
- `$docdiet status` reports `docdiet: ON` or `docdiet: OFF`.
- `$docdiet` reports the state and commands.

When OFF, apply no policy unless the user explicitly requests documentation
cleanup or review. When ON, apply this policy whenever documentation is
relevant to the current task; do not run a separate documentation pass merely
because the toggle is enabled.

## Policy

Document durable information developers, users, operators, or maintainers need:
interfaces and contracts, setup/deployment, configuration, operations,
architectural constraints, invariants, non-obvious behavior, migrations, and
critical warnings. Usually omit implementation trivia, temporary state,
debugging history, task diaries, inferred facts, and redundant summaries.

When behavior changes, replace the existing explanation. Keep one canonical
source for each fact; remove safe duplicates or link to the canonical source.
Retain historical material only when it helps with migration, compatibility,
or architectural rationale.

While touching documentation, clean only nearby material clearly stale,
duplicated, contradictory, superseded, misleading, verbose, or tied to a
removed name, command, file, configuration, or behavior. For renamed or removed
public concepts, one targeted repository search is allowed. Do not inventory
unrelated docs, broadly hunt stale content, or create a separate cleanup pass.

Keep prose lean and examples minimal but complete. Preserve protected docs:
generated docs, changelogs/release notes, licenses, legal material, codes of
conduct, vendored docs, and Markdown containing
`disable-agentic-editing: true` unless explicitly requested.

Before creating a doc, check whether an existing canonical document fits.
Create one only for durable, distinct information with no suitable home.

## Completion check

If documentation was touched, verify that the changed behavior is documented
where needed; touched docs match the implementation; superseded material is
gone; no unnecessary duplication was added; examples and commands are valid;
protected content is unchanged; and the work stayed within scope. Then stop.
