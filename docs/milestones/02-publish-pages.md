# 02: Publish to GitHub Pages

**Status:** planned
**Depends on:** 01

## Goal

The page from milestone 01 is live at `https://<owner>.github.io/<repo>/`.

## Scope

- In: tool checks, creating the GitHub repo, pushing, enabling Pages and checking the live URL.
- Out: custom domain, CI, anything beyond the default Pages build.

## Relevant Design

See [design.md](../design.md) for the repo name and branch decision.

## Tasks

- [ ] Check `gh` is installed and `gh auth status` shows a login. If not, tell the user what to run.
- [ ] Ask for the repo name (default `astro`).
- [ ] Settle the branch: keep `master` and publish Pages from it, or the user renames it with `git branch -m master main`.
- [ ] Give the user a commit message for milestone 01 and the docs. The user commits.
- [ ] Give the user the command to create the GitHub repo and push. The user runs it:
      `gh repo create <repo> --public --source=. --remote=origin --push`
- [ ] Enable Pages from the branch root (Claude runs this after the user confirms the push):
      `gh api -X POST repos/<owner>/<repo>/pages -f "source[branch]=<branch>" -f "source[path]=/"`
- [ ] Poll `gh api repos/<owner>/<repo>/pages/builds/latest` until the build finishes.
- [ ] Fetch `https://<owner>.github.io/<repo>/`, confirm it returns the page and the image URLs load, and give the user the URL.

## Acceptance Criteria

- [ ] The public GitHub repo exists and contains `index.html` and `images/`.
- [ ] Pages is enabled and the latest build succeeded.
- [ ] The live URL shows all images with their titles.

## Notes
