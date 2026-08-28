# Workbench Store

The app store for [Workbench OS](https://github.com/yueranyuan) — an
awesome-list. Each entry: a repo, one line of what it is, and (when
verified) an install recipe. A Workbench instance subscribes to this repo;
its Workbench resident reads the list, prints entries as cards, and
installs on request. Recipes make installs instant; a missing recipe means
the installing resident figures it out — and PRs the recipe back here, so
the first installer anywhere pays the cost once.

## Apps

- [2048](https://github.com/gabrielecirulli/2048) — the classic
  sliding-tile game. Pure static; installs in seconds.
  `recipe: recipes/2048.json`
- [Chess Tutor](https://github.com/yueranyuan/chess-tutor) — play against
  an adjustable Stockfish with instant move-by-move coaching, hot lesson
  policy, and the Coach resident. The flagship.
  `recipe: npm ci && npm run build; static dist/; hot: policy.js, widgets/; resident: coach/CLAUDE.md`
- [IT Tools](https://github.com/CorentinTh/it-tools) — 100+ client-side
  developer utilities, zero backend.
  `recipe: pnpm install --frozen-lockfile && pnpm build; static dist/`
- [Vikunja](https://github.com/go-vikunja/vikunja) — tasks: list, kanban,
  gantt; single Go binary, SQLite.
  `recipe: release binary darwin-arm64; config.yml {publicurl, interface :5302, sqlite}; verified v2.5.0`
- [SilverBullet](https://github.com/silverbulletmd/silverbullet) — notes
  as plain markdown, wiki links, Lua-scriptable. Notes are readable by
  every resident.
  `recipe: PENDING — release sb-*.zip is the client CLI only; server is the repo's deno/rust build, not yet figured out`

## Listed, not yet installed

- [Excalidraw](https://github.com/excalidraw/excalidraw) — whiteboard.
  `recipe: yarn && yarn start (:3000); heavy install`
- [Actual Budget](https://github.com/actualbudget/actual) — local-first
  budgeting; bank sync vendors (SimpleFIN/GoCardless) → run SEALED on
  twins first, graduate through the credential gateway.
  `recipe: pending; vendors: simplefin, gocardless`

## How to list an app

One PR, one line, optional recipe. Listing is curation, not vetting —
Workbench reads every repo before first run, and sealed worlds catch
what reading misses.
