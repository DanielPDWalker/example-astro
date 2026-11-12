# Planning

Overview of all milestones. Each milestone has its own file in [milestones/](milestones/) with full detail. Keep entries here short.

Status: `planned` · `in progress` · `done`

| # | Milestone | Status | Summary | Depends on |
|---|---|---|---|---|
| 01 | [Static page](milestones/01-static-page.md) | planned | Copy 3-4 images into `images/` and write one plain `index.html` with title and object name per image. | none |
| 02 | [Publish to GitHub Pages](milestones/02-publish-pages.md) | planned | Create the public GitHub repo, push, enable Pages and confirm the live URL loads. | 01 |

## Cross-Milestone Notes

- Keep it minimal: plain HTML and a little CSS. No JavaScript, frameworks, thumbnails or lightbox.
- The user runs every git command (commit, push, remote). Claude only runs `git diff`, and gives the exact commands to run.
- The repo is public. Check images for EXIF/GPS data before anything is pushed.
- The local branch is `master`. Milestone 02 must either publish Pages from `master` or have the user rename it to `main` first.
