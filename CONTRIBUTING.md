# Contributing to the Shift iQ docs

This repository is the source for [docs.shiftiq.com](https://docs.shiftiq.com/). Most edits land here from one of two places: the GitBook web editor (synced back to `master` automatically) and pull requests opened directly against this repo. Either way, the conventions below apply.

## Commit messages

Use [Conventional Commits](https://www.conventionalcommits.org/) for any commit you write yourself:

```text
<type>(<scope>): <description>
```

* `type` is one of `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.
* `scope` is optional and lowercase — typically the section being edited (`topics`, `contributors`, `releases`, etc.).
* `description` is lowercase, imperative ("add", not "added"), no trailing period, ~50 chars max.

### GitBook auto-commits

When you publish from the GitBook web editor, GitBook generates commits with subjects like `GITBOOK-80: No subject`. **Do not leave those subjects in place when merging the back-sync branch into `master`.**

Either:

1. Rebase the GitBook branch locally and rewrite the subjects to follow Conventional Commits before merging, or
2. Squash the back-sync into a single Conventional Commits message that describes what changed.

The current `master` history has 178 `GITBOOK-XX: No subject` commits. They make changelog mining impossible. Don't add to that count.

## Page conventions

### Frontmatter

Every page should have YAML frontmatter with at least a `description`. GitBook uses it for search snippets and social-share previews.

```yaml
---
description: One sentence describing the page, ~150 chars max
---
```

### Image alt text

Every `<img>` tag must have a non-empty `alt` attribute. GitBook inserts `<img ... alt="">` by default — fix the alt text before merging.

```html
<figure><img src="../.gitbook/assets/sites-01.png" alt="Sites portal layout"><figcaption></figcaption></figure>
```

### File names

Use lowercase kebab-case file names that match the page title (`how-to-publish-a-course.md`, not `README (3).md` or `HowToPublishACourse.md`). When the GitBook editor generates a `README (N).md` style file, rename it before merging — for example, `git mv "README (4).md" "oct-29-version-25.6-is-live.md"` and update the relevant `SUMMARY.md`.

### SUMMARY.md

Each space (`contributors/`, `topics/`, `developers/`, `guides/`, `releases/`, `staff/`, `starters/`, `operations/`, `embeds/`) has its own `SUMMARY.md`. When you add a new page, add it to the appropriate `SUMMARY.md` in the same PR.

### Terminology

The internal vocabulary is **Toolkit** (Domain / Plugin / Utility / Shell), not **Component**. The customer-facing UI calls it a **toolkit** (one word). Don't write "tool kit".

## Reviewing

Before requesting review:

* [ ] Commit messages follow Conventional Commits (or, for back-syncs, the GitBook subjects have been rewritten).
* [ ] New pages have YAML `description:` frontmatter.
* [ ] New images have descriptive `alt=""` attributes.
* [ ] Renamed or moved pages have their references updated in `SUMMARY.md` and in any pages that link to them.
* [ ] The link-check CI is green.
