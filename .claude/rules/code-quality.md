# Code Quality Rules

## TypeScript

> Keep if TypeScript is detected. Remove otherwise.

- Prefer strict mode. Do not add `@ts-ignore` or `// @ts-nocheck` without a comment explaining why.
- Use explicit return types for exported functions.
- Prefer `interface` over `type` for object shapes.
- No implicit `any` — use proper types or `unknown` with narrowing.

## React

> Keep if React/Next.js is detected. Remove otherwise.

- Components: PascalCase file names (e.g., `UserProfile.tsx`).
- Hooks: camelCase with `use` prefix (e.g., `useAuth.ts`).
- Utilities: camelCase (e.g., `formatDate.ts`).
- Prefer functional components with hooks over class components.
- Colocate component styles, tests, and types in the same directory.

## Next.js

> Keep if Next.js is detected. Remove otherwise.

- Use App Router (`app/` directory) for new pages.
- Use Server Components by default; add `"use client"` only when needed.
- API routes go in `app/api/`.
- Shared UI components go in `components/`, not in `app/`.

## Vue 3

> Keep if Vue 3/Nuxt is detected. Remove otherwise.

- Components: PascalCase file names (e.g., `UserProfile.vue`).
- Composables: camelCase with `use` prefix (e.g., `useAuth.ts`).
- Prefer `<script setup lang="ts">` for single-file components.
- Use `defineProps` / `defineEmits` with typed interfaces.
- Colocate component styles and tests in the same directory.

## Nuxt

> Keep if Nuxt is detected. Remove otherwise.

- Use auto-imports; do not manually import composables from `#imports`.
- Pages go in `pages/`, layouts in `layouts/`, middleware in `middleware/`.
- Server API routes go in `server/api/`.

## Angular

> Keep if Angular is detected. Remove otherwise.

- Use standalone components.
- Services: `*.service.ts`, Guards: `*.guard.ts`, Resolvers: `*.resolver.ts`.
- Prefer signals over RxJS for simple state; keep RxJS for complex async flows.

## Svelte

> Keep if Svelte is detected. Remove otherwise.

- Components: PascalCase file names (e.g., `UserProfile.svelte`).
- Stores go in `src/lib/stores/`.
- Use `$props()` rune for typed props.

## Anti-Patterns

- No `console.log` in production code — use a proper logger.
- No commented-out code blocks — delete them.
- No magic numbers — extract to named constants.
- No deeply nested ternaries — use early returns or extract to variables.

## Linting

> Keep the relevant section below. Remove others during adaptation.

### ESLint

- Run lint before committing. Fix all errors, do not suppress warnings.

### Biome

- Run `biome check --write .` for auto-fixable issues.
- Fix all errors before committing.
