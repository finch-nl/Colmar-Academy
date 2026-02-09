# GitHub Copilot instructions — Colmar-Academy

Purpose
- Help AI coding agents be immediately productive in this repo: a small static website with HTML, CSS and media assets.

Big picture
- Single-page/static site. The root `index.html` is the entry; styles live in `resources/css/style.css`; images and videos are under `resources/images/` and `resources/videos/`.
- There is no build system, package.json, or server-side code. Changes are applied directly to HTML/CSS and static assets.

Key files and examples
- `index.html` — minimal page shell (doctype, head, body). Edit this file to add sections, markup, and asset references.
- `resources/css/style.css` — global reset + base typography and small utilities (see the `*` reset and `img { max-width:100% }` rule). Keep layout and global styles here.
- `resources/images/` and `resources/videos/` — store optimized media here and reference with relative paths from `index.html`.

Developer workflows
- Local preview: prefer VS Code Live Server. Fallback: start a simple HTTP server from the repo root:

  PowerShell / cross-platform:

  ```powershell
  python -m http.server 8000
  ```

- No build step: edits to `index.html` and `resources/css/style.css` are reflected on refresh.

Conventions and patterns (discoverable from the codebase)
- Global reset: `* { margin:0; padding:0; box-sizing:border-box; }` at top of `resources/css/style.css` — keep global spacing and box rules centralized.
- Responsive images: rely on `img { max-width: 100%; height: auto; display: block; }`. When adding images, prefer appropriate width/optimized formats.
- Font stack: use system UI stack already in `style.css` (e.g., `-apple-system, 'Segoe UI', Roboto, Arial`). Follow it for any new typography rules.
- No JavaScript present — introduce JS only if a clear requirement exists, and document why (no framework or bundler expected).

What to avoid
- Do not add node_modules or a bundler unless the project owner requests one. This repo is intentionally simple and static.
- Avoid changing file locations for `resources/*` without updating references in `index.html`.

PR guidance for AI agents
- Make small, focused changes (one feature/fix per PR). Update `index.html`, `resources/css/style.css`, and media files as needed.
- Include a short PR description mentioning the files changed and the reason (e.g., "Add hero section to `index.html` and styles in `resources/css/style.css`").

If something is unclear
- Ask the maintainer if a build tool or JS framework is desired before scaffolding one. If asked to add tooling, document the motivation and provide a minimal reproducible change.

Files to inspect first
- [index.html](index.html)
- [resources/css/style.css](resources/css/style.css)
- [resources/images/](resources/images)

— End of instructions —
