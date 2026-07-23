# campus-admin-web

Admin Web App (AWA) — part of the Campus Digitalization Platform. Split out of the `Omega`
monorepo; see
[campus-platform/docs/Campus platform architecture.md](https://github.com/Z-Zenith/campus-platform/blob/main/docs/Campus%20platform%20architecture.md)
for the full system architecture and `campus-platform/INTEGRATIONS.md` for the compatible
version of `@campus/api-client`.

This repo's history was extracted via `git subtree split`, scoped to `apps/admin-web/` from the
original monorepo — commits that didn't touch this path appear as no-op entries, a known cost of
the split, not a bug.

## Tech stack

React 19 + Vite + TypeScript, Tailwind v4 (`@tailwindcss/vite`), shadcn/ui, Framer Motion,
TanStack Query, Recharts. Lint via oxlint. Same stack as `campus-teacher-web`/`campus-parent-portal`
(shared component library, not shared code — shadcn primitives are currently duplicated per app).

## Build & test

```bash
npm install
npm run dev
npm run build
npm run lint
npm run test
```

## Cross-repo dependencies

`@campus/api-client` is pinned via git tag (`"github:Z-Zenith/campus-api-client#0.1.0"` in
`package.json`), replacing the monorepo-era `file:../../packages/api-client` reference that no
longer resolves post-split. Bump the pinned tag when a new version is cut.

## Code conventions

Match the surrounding code's style and folder layout. Feature IDs referenced in this repo:
AWA-01 through AWA-13 (see the architecture doc's Section 2/7 for the full feature list).
