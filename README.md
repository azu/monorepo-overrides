# npm overrides in monorepo

npm's `overrides` feature does not work as expected in a monorepo. This repository demonstrates the issue.

- [[BUG] Overrides are not applied correctly with workspaces · Issue #4834 · npm/cli](https://github.com/npm/cli/issues/4834)
- [docs: Document that overrides only work in the root `package.json` by s100 · Pull Request #7367 · npm/cli](https://github.com/npm/cli/pull/7367)

```
monorepo-overrides@1.0.0
├─┬ app-a@1.0.0 -> ./packages/app-a
│ └── react@18.1.0
├─┬ app-b@1.0.0 -> ./packages/app-b
│ └── react@18.1.0 invalid: "18.2.0" from packages/app-b
└── react@18.2.0 overridden
```
