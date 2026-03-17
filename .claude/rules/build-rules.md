# Build Rules

## Build Commands

> The adaptation skill replaces commands below with the detected package manager.

| Command | Script |
|---------|--------|
| Install | `npm install` |
| Build   | `npm run build` |
| Dev     | `npm run dev` |
| Test    | `npm test` |
| Lint    | `npm run lint` |
| CI Install | `npm ci` |

## Prohibited

- Do not create alternative build scripts.
- Do not use `--force` or skip dependency checks.
- Do not commit lock file changes without a corresponding package.json change.

## Testing

> Keep the relevant section below. Remove others during adaptation.

### Vitest

- Use `npx vitest run` for full suite.
- For single file: `npx vitest run path/to/file.test.ts`.
- For watch mode: `npx vitest`.

### Jest

- Use `npx jest` for full suite.
- For single file: `npx jest path/to/file.test.ts`.
- For watch mode: `npx jest --watch`.

### Playwright

- Use `npx playwright test` for e2e suite.
- For single spec: `npx playwright test path/to/spec.ts`.
- For UI mode: `npx playwright test --ui`.

### Cypress

- Use `npx cypress run` for e2e suite.
- For single spec: `npx cypress run --spec path/to/spec.ts`.
- For interactive: `npx cypress open`.

## Monorepo

> Remove this entire section if not a monorepo.

Scope commands to specific packages when working in a monorepo:
- Turbo: `{pm} build --filter=<package>`
- Nx: `npx nx run <project>:build`
- pnpm workspace: `{pm} --filter <package> build`

Always verify the affected package builds and tests pass before marking a task complete.
