# {{PROJECT_NAME}}

This is a template for an [Application Repository](PHILOSOPHY.md#3-application-repositories-the-core) based on the [OTAKU Manifesto](PHILOSOPHY.md).

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
Please read more about it in [PHILOSOPHY.md](PHILOSOPHY.md).
See our security policy in [SECURITY.md](SECURITY.md).
