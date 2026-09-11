# vietz-sdk

Turborepo monorepo for the shared libraries used across my Node applications.

## Layout

```
packages/
  example/   placeholder library, delete when the first real one lands
```

## Commands

```sh
pnpm install
pnpm build       # tsc per package
pnpm test        # node:test, runs TypeScript directly
pnpm typecheck
```

## Adding a library

Copy `packages/example`, rename the package to `@vietz-dev/<name>`, and write the code.
