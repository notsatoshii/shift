# Shift

Proactive AI mentor that walks a user from idea to shipped product.

Drives conversation, translates jargon, offers defaults, safety-gates irreversible actions. Persists state across sessions. Hands off to [CAE](https://github.com/notsatoshii/CAE) for the build.

## Status

**v3.0** — Claude Code skill + backend CLI. Extracted from CAE Phase 2.

Tri-interface roadmap:
- **v3.0** — Claude Code skill (shipped)
- **v3.1** — Telegram client via Hermes
- **v3.2** — Web app (part of unified CAE dashboard)

## Install

```bash
git clone git@github.com:notsatoshii/shift.git /home/shift
ln -sf /home/shift/bin/shift /usr/local/bin/shift
ln -sf /home/shift/skills /home/USER/.claude/skills/shift   # for the Claude Code skill
```

## Modes

```
shift new <name>     # new project intake
shift resume         # resume existing project
shift next           # propose + execute next action
shift help           # explain current state, offer 3 fixes
shift status         # done / in-progress / blocked / next
shift learn <topic>  # teach about CAE concepts
```

State persists in `<project-dir>/.shift/state.json`.

## Lifecycle

```
IDEA → (Scout research) → PRD → user approves →
ROADMAP decomposition → user approves → CAE execute → UAT → ship
```

Roadmap is ordered steps only — no timelines, no effort estimates.

## Relationship to CAE

Shift plans; CAE builds. When Shift approves a ROADMAP, it hands off to `cae execute-phase`. CAE's config registers `shift:` as a role and `cae shift <args>` is a passthrough to this CLI — but those integrations live in the CAE repo, not here.

## License

MIT
