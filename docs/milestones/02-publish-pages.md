# 02: Publish to GitHub Pages

**Status:** done
**Depends on:** 01

## Goal

The page from milestone 01 is live at `https://<owner>.github.io/<repo>/`.

## Scope

- In: tool checks, creating the GitHub repo, pushing, enabling Pages and checking the live URL.
- Out: custom domain, CI, anything beyond the default Pages build.

## Relevant Design

See [implemented_design.md](../implemented_design.md) for the repo name and branch decision.

## Tasks

- [x] ~~Check `gh` is installed and `gh auth status` shows a login.~~ `gh` was not installed. The user did everything through `git` and the GitHub web UI instead.
- [x] Ask for the repo name (default `astro`). Chosen: `example-astro`.
- [x] Settle the branch: keep `master` and publish Pages from it, or the user renames it with `git branch -m master main`. Chosen: rename to `main`.
- [x] Give the user a commit message for milestone 01 and the docs. The user commits. (Milestone 01 was already committed in 532cf6d.)
- [x] The user creates the repo and pushes. Done instead by creating an empty public repo on github.com, then `git remote add origin git@github.com:DanielPDWalker/example-astro.git` and `git push -u origin main`.
- [x] Enable Pages from the branch root. The user did this in Settings → Pages (Deploy from a branch, `main`, `/ (root)`) instead of through `gh api`.
- [x] Wait for the build. Claude polled the live URL with `curl` instead of the `gh` builds API. It returned 200 about 50s after Pages was saved.
- [x] Fetch `https://danielpdwalker.github.io/example-astro/` and confirm the page and the image URLs load.

## Acceptance Criteria

- [x] The public GitHub repo exists and contains `index.html` and `images/`.
- [x] Pages is enabled and the latest build succeeded.
- [x] The live URL shows all images with their titles. The page has 4 `<img>` tags and all 4 images return 200 `image/jpeg`.

## Notes

- `gh` is not needed. A plain `git` push plus the web UI covers it.
- Use the SSH remote URL (`git@github.com:...`), not HTTPS. The user authenticates with an SSH key, and an HTTPS remote prompts for a token instead.
- Live URL: https://danielpdwalker.github.io/example-astro/
