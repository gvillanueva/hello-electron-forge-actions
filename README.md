# hello-electron-forge-actions
[![Continuous Integration Checks - Lint, TypeCheck, Build](https://github.com/gvillanueva/hello-electron-forge-actions/actions/workflows/ci.yml/badge.svg)](https://github.com/gvillanueva/hello-electron-forge-actions/actions/workflows/ci.yml)

Boilerplate Electron Forge project configured with TypeScript and webpack. Includes basic GitHub Actions CI for linting, TypeScript type-checking, and a fast build check.

**Status:** Minimal example / starter template

## Quickstart

Prerequisites:
- Node.js 18 or 20 (recommended)
- npm

Install dependencies:

```bash
npm install
```

Run in development (hot-reload via webpack plugin):

```bash
npm start
```

Build/package for testing (unpacked app):

```bash
npm run package
```

Create distributable installers (platform-specific — may require extra tooling):

```bash
npm run make
```

Linting:

```bash
npm run lint
```

## What each script does

- `start` — Run the app in development mode using `electron-forge start` and the webpack renderer/main configs.
- `package` — Produce a platform/arch-specific unpacked app directory under `out/`. Fast and suitable for CI validation.
- `make` — Produce platform installers/archives (DMG, EXE, AppImage, etc.) using configured makers. Runs `package` first and may require platform tooling (codesign, Wine, etc.).
- `publish` — Publish using Electron Forge publishing flow (configure in `forge.config.ts`).
- `lint` — Run ESLint over TypeScript sources.

## Continuous Integration (example)

This repository includes a simple CI workflow that performs the following checks on push and PRs:

- Install dependencies (`npm ci`)
- Run ESLint (`npm run lint`)
- Run TypeScript type-checking (`npx tsc --noEmit`)
- Run a fast package build check (`npm run package`)

## Project layout

- `src/` — TypeScript source files for main, renderer, and preload.
- `webpack.*.ts` — Webpack configs for main and renderer.
- `forge.config.ts` — Electron Forge configuration and makers/plugins.

## Contributing

This is a minimal starter. Feel free to:
- Add tests and CI coverage steps
- Add platform-specific maker configurations for `make`
- Update Node/Electron versions as needed

## License

MIT
