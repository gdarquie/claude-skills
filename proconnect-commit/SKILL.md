---
name: proconnect-commit
description: Commit msg convention for ProConnect federation repo. Use when creating/amending a commit there.
---

# ProConnect commits

## Title

`<gitmoji> <Short description>`

- Gitmoji first (♻️ refactor, 🐛 fix, ✨ feat, 🔥 removal, 🔒 security, ⬆️ deps, 📝 docs, ✅ tests, 🔧 cfg).
- Capitalized, usually imperative verb, no trailing period.

## Body

EN, shortest possible:

```
**Problem**

<Why change needed. 1 short paragraph.>

**Proposal**

<What commit does. 1 paragraph or few bullets.>
```

- No details diff already shows (option names, flags).
- Wrap ~72 chars. Code/pkgs/apps in backticks.

## Example

```
♻️ Run statisticat with native Node TypeScript

**Problem**

Statisticat was not aligned with `hybridge`: it needed a `tsc` build step
for production, `tsx` to run in dev, and Babel only to let Jest read
TypeScript. Node 26 strips types natively, so all of this was useless.

**Proposal**

Run the `.ts` sources directly with Node, as `hybridge` does:

- drop Babel, Jest and `tsx`, and migrate the tests to `node:test`
- use `tsc` for type checking only
- remove the build stage from the Dockerfile
```
