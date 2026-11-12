# Design

Active design: planned work and decisions not yet implemented. When something is implemented, move it to [implemented_design.md](implemented_design.md).

## Decisions

- The user runs all git commands, including `gh repo create ... --push`, because that command pushes. Claude runs only the `gh` checks, the Pages API call and the live URL check.
- Pages publishes from the repo root of `main`. The user renames the local `master` branch to `main` before the first push. The repo is called `example-astro`.

## Planned
