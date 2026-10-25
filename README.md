# {{PROJECT_NAME}}

The Application Repository is the core of the business logic.
This is a template for an [Application Repository](https://otakumanifesto.org/shapes/) based on the [OTAKU Manifesto](https://otakumanifesto.org/manifesto/).

## Characteristics
- **The Core**: Implementation of the Business Heart.
- **Clean Architecture**: Organized into Domain, Application, Infrastructure, and Interface layers.
- **DDD Focused**: Logic driven by the business domain.
- **Lean**: Generic tools are offloaded to Atomic Repositories.

## Structure
- `src/Domain`: Entities and business rules.
- `src/Application`: Use cases and orchestration.
- `src/Infrastructure`: External adapters (DB, Mail, etc.).
- `src/Interface`: Entry points (Controllers, CLI).

## Installation

To create a new Application Repository using this template:

```bash
composer create-project otaku/application <project-name>
```

## Running

```bash
php -S localhost:8000 -t public
```

## Philosophy
We follow **The OTAKU Manifesto: Fluid Structure Design**.
Please read more about it in [OTAKU Manifesto](https://otakumanifesto.org/manifesto/).
See our security policy in [SECURITY.md](SECURITY.md).

## Documents

- [OTAKU Manifesto](https://otakumanifesto.org/manifesto/) — the doctrine.
- [OTAKU Guide](https://otakumanifesto.org/guide/) — how to apply the rules.
- [`docs/GITFLOW.md`](docs/GITFLOW.md) — git workflow.
- [`docs/STATE.md`](docs/STATE.md), [`docs/ROADMAP.md`](docs/ROADMAP.md), [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — project state.
