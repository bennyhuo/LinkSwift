# AGENTS.md

## Project Overview
- `LinkSwift` is a CommonJS JavaScript userscript project for generating download links from multiple cloud storage providers.
- The primary script entrypoint is `（改）网盘直链下载助手.user.js`.
- An auxiliary companion script exists at `（改）百度网盘会员青春版.user.js`.
- Remote/provider-specific configuration lives under `config/*.json`.
- Shared styling is in `default.min.css`.

## Working Conventions
- Prefer small, targeted edits. This repository is mostly distributed as single-file userscripts, so avoid broad refactors unless requested.
- Keep userscript metadata headers intact and consistent when editing script files.
- Preserve existing Chinese user-facing copy unless the task explicitly asks for wording changes.
- When changing provider behavior, inspect the matching JSON in `config/` and any related script logic together.
- Avoid renaming the published script files unless explicitly requested; their filenames are part of the distribution surface.

## Validation
- Install dependencies with `npm install` if needed.
- Run lint autofix with `npm run check`.
- `npm test` is intentionally not implemented and currently exits with an error.
- There is no formal test suite in the repository, so for behavior changes, document what was validated manually.

## File Map
- `（改）网盘直链下载助手.user.js`: main userscript implementation.
- `（改）百度网盘会员青春版.user.js`: supplementary Baidu-specific userscript.
- `config/config.json`: shared configuration.
- `config/*.json`: provider-specific configuration.
- `default.min.css`: shared styles injected by the script.
- `eslint.config.mjs`: lint configuration.
- `README.md`: primary project documentation and release notes.

## Editing Notes
- Treat the repository as release-oriented: script compatibility and metadata correctness matter more than architectural purity.
- Check for duplicated literals and provider-specific branches before changing shared download logic.
- If updating documented behavior, keep `README.md` in sync with user-visible functionality.
