# AGENTS.md

> **Before you start:** read [`docs/STATE.md`](docs/STATE.md) to know where the
> project stands, what was decided and the next steps. For what hasn't started
> yet, see [`docs/ROADMAP.md`](docs/ROADMAP.md). The code layout is in
> [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

## Documents that drive development

| Document | When to consult |
|---|---|
| [`docs/PHILOSOPHY.md`](docs/PHILOSOPHY.md) | **Always.** It holds the unbreakable rules. All development is driven by it. |
| [`docs/GUIDE.md`](docs/GUIDE.md) | When in doubt about **how to apply** a rule from PHILOSOPHY. If there is no clear example, decide together and add the example to the GUIDE. |
| [`docs/GITFLOW.md`](docs/GITFLOW.md) | For **any git operation** (branch, commit, PR, tag, release). If a situation has no guidance, ask how to proceed and then add it to the document. |
| [`docs/STATE.md`](docs/STATE.md) | When resuming work. Tells where we stopped and what was decided. |
| [`docs/ROADMAP.md`](docs/ROADMAP.md) | To know what hasn't started yet. |
| [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) | To understand the layers, flow and contracts before touching the code. |

## What this project is

An OTAKU **Application** repository. Read `composer.json` for the exact PHP and
dependency versions.

## Architecture (summary)

Dependencies point **inward**, towards the `Domain`:

```
Interface  →  Application  →  Domain
Infrastructure  ──────────────┘
```

- `Domain/` — the heart. Entities, value objects, contracts (interfaces) and
  exceptions. Does **not** know about HTTP, JSON or files.
- `Application/` — use cases. Orchestrates the domain. Depends only on `Domain` contracts.
- `Infrastructure/` — adapters. Implements the `Domain` contracts.
- `Interface/` — entry points. Controllers, CLI, etc.

Details in [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

## Code rules (non-negotiable)

The 9 Object Calisthenics rules of [`docs/PHILOSOPHY.md`](docs/PHILOSOPHY.md) are
mandatory. In short:

1. One level of indentation per method.
2. No `else`.
3. Wrap primitives and strings (value objects).
4. First-class collections.
5. One dot per line (Law of Demeter).
6. Don't abbreviate.
7. Small entities (≤50 lines per class, ≤10 files per package).
8. At most 2 instance variables per class.
9. No getters/setters/properties.

## Conventions

- **Strict types:** `declare(strict_types=1);` in every file.
- **No comments** in code. The code must explain itself; the "why" goes in the commit or the GUIDE.
- **Attributes** instead of annotations (`#[Override]`).
- **Interfaces** for public methods.
- **No `switch/case`.** Use `match` or polymorphism.
- **No generic types** (`mixed`, `object`, `array`) when there is an alternative.
  When unavoidable, annotate with generics in the docblock.
- **PHP tag:** only `<?php` on the first line, `declare(strict_types=1);` on the
  third, namespace, and **never** close with `?>`.
- **Cleanliness:** remove unused imports, comments, variables and private functions.

## Workflow

- Run tests with `vendor/bin/phpunit`.
- Run static analysis with `vendor/bin/psalm`.
- A feature is only done when it has a test that exercises it **as a caller would
  use it** (a service call or an HTTP request), not merely "it didn't throw".

## Discover, don't guess

- Read the installed code under `vendor/` before assuming an API.
- Use grep/search to locate what already exists before creating something new.
- If the task doesn't specify something, **ask** instead of guessing. If there is
  no interactive channel, state the assumption and pick the simplest option.
