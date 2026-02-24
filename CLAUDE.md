# CLAUDE.md — AI Assistant Guide for myfamily

This file provides guidance for AI assistants working on this repository.

## Project Overview

**myfamily** is a simple static HTML family homepage written primarily in Korean. It introduces four family members through individual pages linked from a central index. There are no build tools, frameworks, package managers, or backend components of any kind.

## Repository Structure

```
myfamily/
├── index.html   # Main landing page — navigation + family intro + YouTube embed
├── 1.html       # Profile page for 태을 (son)
├── 2.html       # Profile page for 지호 (daughter)
├── 3.html       # Profile page for 영현 (dad)
├── 4.html       # Profile page for 윤경 (mom)
├── sun.jpg      # Family photo (JPEG, 2592×3872 px)
├── README.md    # Minimal readme (contains only the project title)
└── CLAUDE.md    # This file
```

## Technology Stack

| Layer      | Technology                    |
|------------|-------------------------------|
| Language   | HTML5                         |
| Styling    | Inline CSS only (no stylesheet) |
| Scripting  | None                          |
| Framework  | None                          |
| Build tool | None                          |
| Package mgr| None                          |
| Testing    | None                          |

## Page Anatomy

### index.html
- Site title: "My Famaily" (note: intentional or typo — preserve as-is unless asked to fix)
- Navigation `<ul>` linking to all four member pages
- Brief Korean family intro paragraph
- Embedded YouTube video (`<iframe>`)

### Member pages (1.html – 4.html)
Each member page follows an identical pattern:
1. Site title heading linking back to `index.html`
2. Shared navigation `<ul>` (copy-pasted across all pages — there is no shared template/include)
3. Member name as `<h1>`
4. One-sentence Korean description of the member

| File   | Name | Role         | Description (Korean)                          |
|--------|------|--------------|-----------------------------------------------|
| 1.html | 태을 | Son          | 아들, 잘생겼고 만들기를 잘해요                |
| 2.html | 지호 | Daughter     | 딸, 이쁘고 노래를 잘 불러요                   |
| 3.html | 영현 | Dad          | 아빠, 좀 뚱뚱하긴 하지만 잘생겼어요           |
| 4.html | 윤경 | Mom          | 엄마, 잠을 많이 자서 그런지 이뻐요            |

## Known HTML Quirks

The existing markup contains several non-standard patterns. **Do not "fix" these unless explicitly asked**, as they reflect the current working state of the site:

- `<h1>` elements nested inside `<li>` items within a `<ul>`
- `<h1>` elements nested inside `<p>` elements
- Uppercase closing tags (`</P>`) mixed with lowercase opening tags
- A space before `=` in `<meta charset ="utf-8" />`
- Site title spelt "Famaily" (not "Family") — present in every page

## Character Encoding

All pages declare `UTF-8` encoding via `<meta charset="utf-8" />`. Always preserve this declaration when editing any HTML file, as all Korean content depends on it.

## Development Workflow

### Viewing the site
Open any HTML file directly in a browser — no server or build step is required:

```bash
# Example (Linux/macOS)
xdg-open index.html     # Linux
open index.html         # macOS
```

### Editing pages
- Edit files directly; there is no compilation or transpilation step.
- Navigation is **duplicated** in every file. If you add a new page or rename a link, update the `<ul>` block in **every** HTML file.

### Adding a new family member
1. Create a new HTML file (e.g., `5.html`) using the same structure as `1.html`–`4.html`.
2. Add a corresponding `<li>` to the navigation `<ul>` in **all** existing HTML files (including `index.html`).

### Adding images
Place image files in the root directory alongside the HTML files and reference them with a relative path (e.g., `<img src="photo.jpg">`).

## Git Conventions

- **Default branch:** `master`
- **Remote:** `origin` (via local HTTP proxy at `127.0.0.1:55450`)
- Feature/task branches follow the pattern `claude/<description>-<session-id>`
- Commit messages are short and descriptive in English (see existing history)

## No Testing or CI

There are no automated tests, linters, or CI pipelines. Manual browser verification is the only testing approach.

## Content Language

Page content is written in Korean (한국어). Preserve Korean text accurately when editing. Do not translate content unless explicitly requested.
