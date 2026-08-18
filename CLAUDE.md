# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is **Rohit Kushwaha's GitHub Profile Repository** (`DevRohit06/DevRohit06`). The README.md is
rendered as the GitHub profile page. There is no application code, build system, or test suite.

The profile is built as a **navigable terminal**: `README.md` is the boot screen, and every command
on it links to a screen under `cmd/`. Nothing executes — GitHub's sanitiser allows no JavaScript, so
the interactivity is a state machine made of hyperlinks between markdown files.

## Structure

- `README.md` — boot screen: banner, a neofetch block, the command list
- `cmd/*.md` — one file per command (`help`, `man`, `now`, `3d`, `blog`, `connect`, `projects`)
- `cmd/p/*.md` — one screen per project, reached from `cmd/projects.md`
- `assets/bars.stl` — the banner motif as a 3D mesh, rendered natively by GitHub
- `.github/workflows/blog-post-workflow.yml` — hourly Action; writes into **`cmd/blog.md`**
  (not README.md) via the action's `readme_path` input

## Rules that are easy to get wrong

- **Use `​```console`, never `​```ansi`.** GitHub does *not* render ANSI escape codes in markdown —
  they stay literal and the screen fills with `←[1m` garbage. `console` (shell-session) highlighting
  colours the prompt, the command and the output separately, using the *viewer's* theme, so the
  terminal reads correctly in both light and dark mode. For that to work, lines must look like a
  real transcript: `rohit@github:~$ command`, then output beneath it.
- **Navigation links must be absolute** (`https://github.com/DevRohit06/DevRohit06/blob/main/...`).
  Relative links do not resolve when a README is rendered on the *profile* page.
- `​```stl` and `​```mermaid` are rendered by GitHub client-side. Verify changes to them on a branch
  before merging — the page source contains `js-render-enrichment-target` when a block will be
  enriched, and does not when it won't.
- Keep ASCII under ~64 columns so it does not overflow on mobile.
- The list between `<!-- BLOG-POST-LIST:START -->` and `<!-- BLOG-POST-LIST:END -->` in
  `cmd/blog.md` is machine-written. Do not edit it by hand.

## Facts worth not getting wrong

- He is a **core contributor** to `pocketpaw/pocketpaw` (873★), with 294 merged PRs — **not** its
  creator.
- `discli` publishes to PyPI as **`discord-cli-agent`**; the `discli` name there is someone else's.
- Lito publishes to npm as **`@litodocs/cli`**.
- `astryx-svelte` is **10 npm packages** under the `@astryx-svelte` scope, not one.
- `astryx-svelte` is an unofficial port, not affiliated with Meta. Say so.
