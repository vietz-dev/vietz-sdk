# vietz-sdk

Turborepo monorepo for the shared libraries used across the vietz-dev applications.

## Layout

```
packages/
  auth/               Better Auth stack (Prisma, OIDC, tenant context) + Effect service
  hono-effect/        Effect runtime adapter for Hono handlers
  typescript-config/  shared tsconfig base for consuming applications
```

## Commands

```sh
pnpm install
pnpm build       # tsc per package, emits dist/
pnpm test        # vitest per package
pnpm typecheck
```

## Publishing

Packages are published to GitHub Packages under the `@vietz-dev` scope. Consumers
need `@vietz-dev:registry=https://npm.pkg.github.com` in their `.npmrc` and a
GitHub token with `read:packages`.

```sh
pnpm build
pnpm -r publish --access restricted
```

## Adding a library

Copy an existing package, rename it to `@vietz-dev/<name>`, and write the code.
Relative imports need the `.js` extension: the packages emit `nodenext` ESM.
