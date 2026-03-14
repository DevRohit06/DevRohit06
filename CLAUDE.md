# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is **Rohit Kushwaha's GitHub Profile Repository** (`DevRohit06/DevRohit06`). The README.md is rendered as the GitHub profile page. There is no application code, build system, or test suite.

## Structure

- `README.md` — The profile page content (skills, social links, blog posts, Spotify embed)
- `banner.png` — Profile banner image
- `.github/workflows/blog-post-workflow.yml` — Hourly GitHub Action that fetches latest blog posts from `https://www.rohitk06.in/rss.xml` and updates the README (uses `gautamkrishnar/blog-post-workflow`)
- `.github/workflows/snake.yml` — Generates GitHub contribution snake animations every 12 hours, pushes SVG/GIF outputs to the `output` branch

## Key Details

- **Blog posts section** in README is auto-generated — do not manually edit content between the `<!-- BLOG-POST-LIST:START -->` and `<!-- BLOG-POST-LIST:END -->` markers
- The snake workflow outputs to a separate `output` branch via GitHub Pages
- RSS feed source for blog posts: `https://www.rohitk06.in/rss.xml` (max 4 posts displayed)
- Most commits are automated (blog post updates from the workflow)
