# Planning

Overview of all milestones. Each milestone has its own file in [milestones/](milestones/) with full detail. Keep entries here short.

Status: `planned` · `in progress` · `done`

| # | Milestone | Status | Summary | Depends on |
|---|---|---|---|---|
| 01 | [Static page](milestones/01-static-page.md) | done | Copied 4 Seestar S50 images (EXIF stripped) into `images/` and wrote one plain `index.html` that captions each image with its filename. | none |
| 02 | [Publish to GitHub Pages](milestones/02-publish-pages.md) | done | Created public repo `example-astro`, pushed `main` over SSH, enabled Pages in the web UI. Live at https://danielpdwalker.github.io/example-astro/. | 01 |

## Cross-Milestone Notes

- Keep it minimal: plain HTML and a little CSS. No JavaScript, frameworks, thumbnails or lightbox.
- The user runs every git command (commit, push, remote). Claude only runs `git diff`, and gives the exact commands to run.
- The repo is public. Strip EXIF/GPS from any image before it is added to `images/` (done for the first four in 01).
- The branch is `main`, and Pages publishes from its root. Pushing to `main` updates the live site.
