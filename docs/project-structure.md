# Project structure — explanation and purpose

This document explains the recommended repository layout and the purpose of each folder/file. Use it as a quick guide when adding features, tests, or CI.

## High-level tree
my-project/
- src/                — application source code
- tests/
  - unit/             — fast, isolated unit tests
  - integration/      — tests that exercise multiple modules or external services
- docs/               — documentation and design notes
- scripts/            — helpful scripts (setup, build, deploy helpers)
- .github/workflows/  — CI/CD pipeline definitions (GitHub Actions)
- .vscode/            — editor settings and recommended extensions
- package.json        — npm/Yarn metadata and scripts
- tsconfig.json       — TypeScript compiler settings
- jest.config.js      — test runner configuration
- CONTRIBUTING.md     — how to contribute
- LICENSE             — project license
- README.md           — high-level project overview and quick start

## Folder/file purposes

- src/
  - Contains all source code. Organize by feature or by technical layer (e.g., modules, services, api).
  - Keep files small and focused. Export a public surface for each module.

- tests/
  - unit/: Tests that run quickly and mock external dependencies. Should be isolated.
  - integration/: Tests that spin up multiple components or hit external services (use test/staging endpoints).

- docs/
  - Architecture, design decisions, API contracts, onboarding notes. Prefer plain Markdown for readability.

- scripts/
  - Shell or Node scripts used for setup, release, local dev helpers. Name them clearly (e.g., setup-dev.sh, release.sh).

- .github/workflows/
  - CI definitions. Keep builds fast: run lint + unit tests on PRs, full integration e2e on merges or scheduled runs.

- .vscode/
  - Team editor settings (formatting rules, recommended extensions). Keeps contributors consistent.

- package.json
  - Scripts: keep common scripts like "start", "build", "test", "lint".
  - DevDependencies: test runners, linters, formatters.

- tsconfig.json / jest.config.js
  - Centralize compile and test behaviour. Reference them from CI configs.

- CONTRIBUTING.md
  - Explain branch strategy, commit message style, PR checklist, and how to run tests locally.

- README.md
  - Quick start: prerequisites, install, run tests, run app, and where to find docs.

## Recommended next steps
1. Move existing source into src/ and tests into tests/.
2. Add or update README.md with run steps.
3. Add linting (ESLint + Prettier) and a basic GitHub Actions workflow to run tests on PRs.
4. Create CONTRIBUTING.md with a simple PR checklist.
5. Keep docs/ up to date for architecture decisions.

## Conventions
- One responsibility per file.
- Prefer feature folders (featureX/index.ts, featureX/service.ts) for large apps.
- Tests are colocated by type (unit/integration); consider colocating unit tests next to implementation for small modules.
