## Repo Shape

- Runtime is just `index.html` + `game.js`; there is no bundler, module system, package manifest, or generated code.
- `index.html` is the only HTML entrypoint and loads `game.js` with a plain `<script>` tag.
- Almost all behavior is centralized in `game.js`: input handling, entity classes, game state, update loop, and rendering.

## Run And Verify

- Fastest manual check: open `index.html` directly in a browser.
- Optional local server from the README: `npx serve .`, then open `http://localhost:3000`.
- There is no repo-local test, lint, or typecheck command to run.

## Editing Notes

- Keep changes browser-compatible without build tooling; do not introduce imports, npm-based assumptions, or framework setup unless the user asks for a larger refactor.
- Preserve the current fixed canvas contract unless intentionally changing gameplay/rendering boundaries: `800x600` in `index.html`, mirrored by `W = 800` and `H = 600` in `game.js`.
- UI text and on-screen labels are currently in Spanish; keep new player-facing copy consistent unless asked otherwise.
