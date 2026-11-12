# Design

Active design: planned work and decisions not yet implemented. When something is implemented, move it to [implemented_design.md](implemented_design.md).

## Decisions

- The site lives in this existing local repo. The brief said to make a new folder, but this repo replaces that step.
- The user runs all git commands, including `gh repo create ... --push`, because that command pushes. Claude runs only the `gh` checks, the Pages API call and the live URL check.
- Pages publishes from the repo root of the default branch. The branch name (`master` or `main`) is decided at the start of milestone 02.
- Images are served as-is. They are resized or converted only if one is over 25 MB and the user agrees.

## Planned

### Page layout (milestone 01)

- One `index.html` at the repo root, with a small `<style>` block and no JavaScript.
- Dark background with light text.
- One block per image, in the order the user gives:
  - The image, scaled to fit the page width (`max-width: 100%; height: auto`), wrapped in a link to the full file in `images/`.
  - The capture title.
  - The object name.
- Each image has `alt` text built from the title and object name.
