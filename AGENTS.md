# AGENTS.md

## Cursor Cloud specific instructions

This repo is a Cursor training kit (Japanese). The only runnable product is `sample-app/`,
a **static, vanilla HTML/CSS/JS Todo app** with no build step, no package manager, and no
external dependencies. Everything else (`exercises/`, `docs/`) is Markdown learning material.

### Running the app

There is no `package.json`, bundler, or backend. Serve the static files and open them in a browser.
The README's documented command (`start src\index.html`) is Windows-only; in this Linux VM use a
static server instead:

```bash
cd sample-app/src
python3 -m http.server 8000
# open http://localhost:8000/index.html
```

- Opening `index.html` via a `file://` path also works, but serving over HTTP is the reliable way
  to reach it from the Desktop/browser pane.
- App data persists in `localStorage` under the key `cursor-practice-todos`. State survives reloads
  but is per-browser-profile; to reset, clear that key (or run in a fresh profile).

### Lint / test / build

- **No test suite, no linter, and no build system exist** in this repo. There is nothing to run for
  lint/test/build. Validate changes by loading the app in a browser and exercising add / complete /
  delete / reload-persistence manually.
- Code conventions for `sample-app` are enforced only by the rule at
  `.cursor/rules/sample-app-conventions.mdc` (vanilla JS only, `const`/`let` not `var`,
  `console.warn`/`console.error` not `console.log`, kebab-case CSS, primary color `#2563eb`).
- A manual QA checklist lives at `.cursor/skills/todo-app-check/SKILL.md`.
