# 01: Static page

**Status:** planned
**Depends on:** none

## Goal

A single `index.html` in this repo that shows each astrophotography image with its capture title and object name.

## Scope

- In: copying the images into `images/`, the EXIF/GPS check, and `index.html`.
- Out: GitHub repo creation and Pages, deferred to [02](02-publish-pages.md).

## Relevant Design

See [design.md](../design.md) for the page layout.

## Tasks

- [ ] Ask the user for the image folder path and, per image, a title and object name (e.g. "Andromeda Galaxy, 3 hours of data" / "M31").
- [ ] Copy the images into `images/` in this repo. Leave the originals untouched.
- [ ] Check file sizes. If any file is over 25 MB, tell the user and ask before resizing or converting. Otherwise don't touch the files.
- [ ] Check each image for EXIF/GPS data and report what is there. The user decides whether to strip it before milestone 02.
- [ ] Write `index.html` as described in the design.
- [ ] Open the page locally to check it renders.

## Acceptance Criteria

- [ ] All images display in `index.html` opened from disk, each with its title and object name.
- [ ] Each image links to its full-size file.
- [ ] The page has no JavaScript and no external dependencies.
- [ ] The user has seen the EXIF/GPS report.

## Notes
