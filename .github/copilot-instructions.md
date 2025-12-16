# Copilot / AI Agent Instructions for domraalt

Purpose
- This is a very small, static website repository. The single authoritative page is `index.html` in the repository root. A `CNAME` file indicates the site is published with a custom domain via GitHub Pages.

Big picture
- Single-page static site: edits are usually to `index.html` (markup + inline styles/scripts). There are no build tools, package manifests, or test runners present.
- Deployment: repository is intended to be served from the repository root (GitHub Pages). Do not remove or alter the `CNAME` file unless the user explicitly requests a domain change.

Developer workflows (what works here)
- Local preview: run a simple static server in the repo root, for example:

  python3 -m http.server 8000

- Quick edits: make small, focused changes to `index.html` and open in a browser.
- Avoid adding heavy JS frameworks, build systems, or CI unless requested — this repo is intentionally minimal.

Project-specific conventions
- Keep changes minimal and self-contained: prefer editing `index.html` over introducing many new files.
- If you must add assets (images, CSS), place them in a top-level folder named `assets/` and reference them with relative paths.
- Branch naming: use short, descriptive branches like `feature/fix-typo-index` or `chore/add-asset-logo`.

Integration points & external dependencies
- There are no declared package or external dependency files. Any external CDN usage should be explicit in `index.html` and justified in the PR description.

Recommended PR guidance for AI agents
- Create small, focused PRs that change 1–2 files only (usually `index.html` and optionally `assets/...`).
- In the PR description include: motivation, exact files changed, preview steps (e.g., `python3 -m http.server 8000`), and a note if the `CNAME` was modified.

Examples (concrete patterns seen in this repo)
- Edit text/content inside `index.html` and add minimal inline styles. If adding a stylesheet, add `assets/styles.css` and link with a relative path.

What not to do
- Do not scaffold Node projects, add `package.json`, or introduce build tooling without an explicit request.
- Do not change `CNAME` unless asked.

If anything is unclear
- Open `index.html` first to confirm the structure and any existing inline scripts/styles.
- Ask the repository owner about publishing details before making deployment-related changes.

Feedback
- After making changes, leave a brief comment in the PR describing how you locally validated the site (browser + local static server command).

-- end --
