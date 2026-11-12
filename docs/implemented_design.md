# Implemented Design

Archive of implemented design and decisions, moved here from [design.md](design.md). Reference only.

## Decisions

- The site lives in this existing local repo. The brief said to make a new folder, but this repo replaces that step.
- Images are served as-is. They are resized or converted only if one is over 25 MB and the user agrees.
- Each image is named `<object>, Seestar S50, <date taken>.jpg`, and that name is its only caption. This replaced the planned separate title and object name.
- Images in `images/` have EXIF/XMP stripped before they are committed, because the camera writes GPS coordinates.
- The user runs every git command and creates the repo and Pages settings in the GitHub web UI. `gh` is not used. This replaced the planned `gh repo create` and `gh api` steps.
- The repo is `DanielPDWalker/example-astro` (public), with an SSH remote. The branch is `main` (renamed from `master`).

## Implemented

### Page layout (milestone 01)

- One `index.html` at the repo root, with a small `<style>` block and no JavaScript.
- Heading "Example Astrophotography", dark background, light text, content capped at 900px wide.
- One `<figure>` per image, in date order:
  - The image, scaled to fit the page width (`max-width: 100%; height: auto`), wrapped in a link to the full file in `images/`. Spaces in the URLs are encoded as `%20`.
  - A caption with the filename minus `.jpg`, also used as the `alt` text.

### Publishing (milestone 02)

- GitHub Pages, "Deploy from a branch", `main`, `/ (root)`. There is no build step or workflow file.
- Live at https://danielpdwalker.github.io/example-astro/. Every push to `main` redeploys it within about a minute.
