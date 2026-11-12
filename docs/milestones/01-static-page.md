# 01: Static page

**Status:** done
**Depends on:** none

## Goal

A single `index.html` in this repo that shows each astrophotography image with its capture title and object name.

## Scope

- In: copying the images into `images/`, the EXIF/GPS check, and `index.html`.
- Out: GitHub repo creation and Pages, deferred to [02](02-publish-pages.md).

## Relevant Design

See [design.md](../design.md) for the page layout.

## Tasks

- [x] Ask the user for the image folder path and, per image, a title and object name. Changed: one descriptive title per image, used as the filename (see Notes).
- [x] Copy the images into `images/` in this repo. Leave the originals untouched.
- [x] Check file sizes. If any file is over 25 MB, tell the user and ask before resizing or converting. Otherwise don't touch the files.
- [x] Check each image for EXIF/GPS data and report what is there. The user decides whether to strip it before milestone 02.
- [x] Write `index.html` as described in the design.
- [x] Open the page locally to check it renders.

## Acceptance Criteria

- [x] All images display in `index.html` opened from disk, each captioned with its filename (title).
- [x] Each image links to its full-size file.
- [x] The page has no JavaScript and no external dependencies.
- [x] The user has seen the EXIF/GPS report.

## Notes

- Source: 4 JPEGs from the Downloads folder, all from a ZWO Seestar S50, all under 2 MB, so no resizing.
- The user chose to drop the separate title and object name. Each file is named with a descriptive title (`<object>, Seestar S50, <date taken>.jpg`) and the page shows that filename without `.jpg`. Object names and dates came from the EXIF `ImageDescription` and `DateTimeOriginal` tags.
- Exposure time was left out. The EXIF value is total stacking time for one image and single-frame time for the others.
- All four originals had GPS coordinates. The user agreed to strip them, so the copies in `images/` have their APP1 (EXIF/XMP) segments removed. The pixel data was copied byte for byte. The originals are unchanged.
- Page heading: "Example Astrophotography".
