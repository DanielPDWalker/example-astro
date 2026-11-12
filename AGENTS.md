# Astro Image Hosting

This file is the single source of project instructions. `CLAUDE.md` imports it; keep shared instruction updates here.

## Docs Workflow

All planning and design lives in `docs/`. Keep context lean: read only what the current task needs.

| File | Purpose |
|---|---|
| `docs/planning.md` | Overview of all milestones: order, status, one-line summary, cross-milestone dependencies. Read this first for any milestone work. |
| `docs/milestones/NN-name.md` | One file per milestone: goal, scope, tasks, acceptance criteria. Contains only what that milestone needs; link to other milestones rather than duplicating. |
| `docs/design.md` | Active design: planned work and decisions not yet implemented. |
| `docs/implemented_design.md` | Archive of implemented design and decisions. Reference only; don't load unless needed. |

### Working on a milestone

1. Read `docs/planning.md`, then the milestone's file. Only open other milestone files or `implemented_design.md` if referenced or needed.
2. Do the work.
3. On completion, update the docs as required:
   - Mark the milestone done in `planning.md` and adjust any later milestones affected by what was learned or changed.
   - Tick off tasks / note deviations in the milestone file.
   - Move implemented sections from `design.md` into `implemented_design.md`.
   - Record any new decisions in `design.md` (if still pending) or `implemented_design.md` (if implemented).
   - Update `README.md` if run / test / setup steps changed. Keep it short.

New milestones: copy `docs/milestones/_template.md` and add a row to `planning.md`.

## Images

- The repo is public. Strip EXIF/XMP from every image before it goes into `images/`, because the Seestar S50 writes GPS coordinates. Copy from the original and leave the original untouched.
- After stripping, check the copy has no EXIF block left.
- Never write GPS coordinates or other location data into any file in the repo, docs included.

## Git

- The only git command allowed is `git diff` (to see what has changed). Never run any other git command.
- After each piece of work (planning or a milestone implementation), give a commit message in a code block for the user to commit themselves.
- Format: a single line of two sentences: first what changed or is new, second why.

```
Add milestone docs structure and planning overview. Keeps each milestone's context small so work can focus on one milestone at a time.
```
