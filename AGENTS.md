# Repository Guidelines

## Project Structure & Module Organization
- `src/components/` contains reusable UI components (for example `button/` and `slider/`).
- `src/components/index.ts` and component-level `index.ts` files are the public export surface.
- `src/styles/` contains global SCSS partials (`_boilerplate.scss`, `_typography.scss`) and `index.scss`.
- `.storybook/` holds Storybook configuration used for local component development and docs.
- Build tooling lives at the root: `vite.config.ts`, `tsconfig*.json`, ESLint/Prettier/Stylelint configs.

## Build, Test, and Development Commands
- `pnpm start`: run Vite app locally.
- `pnpm dev`: run Storybook at `http://localhost:6006`.
- `pnpm build`: create library output in `dist/` with Vite + TypeScript declarations.
- `pnpm preview`: preview the Vite build locally.
- `pnpm build-storybook`: generate static Storybook output.
- `pnpm lint` / `pnpm lint:fix`: check or auto-fix lint issues.

## Coding Style & Naming Conventions
- Language: TypeScript + React (`.tsx`) and SCSS modules.
- Formatting/linting: Prettier (`.prettierrc.cjs`), ESLint (`.eslintrc.cjs`), Stylelint (`.stylelintrc.cjs`).
- Use 2-space indentation and keep imports grouped: external packages first, then local modules.
- Component folders use lowercase names (`button`, `slider`); exported React components use PascalCase.
- Prefer `*.module.scss` for component styles; keep shared tokens/rules in `src/styles/`.

## Testing Guidelines
- No dedicated unit-test runner is configured yet.
- Treat Storybook stories (for example `button.stories.tsx`) as the baseline for visual/behavior checks.
- Before opening a PR, run `pnpm lint`, `pnpm build`, and `pnpm build-storybook`.
- When adding tests later, place them next to components using `*.test.ts(x)` naming.

## Commit & Pull Request Guidelines
- Repository currently has no commit history; use Conventional Commits going forward (for example `feat: add icon button variant`, `fix: correct slider thumb focus state`).
- Keep commits focused and scoped to one change.
- PRs should include: clear summary, related issue/ticket, screenshots or Storybook links for UI changes, and a short validation checklist of commands run.
- Request review only after lint/build succeed locally.
