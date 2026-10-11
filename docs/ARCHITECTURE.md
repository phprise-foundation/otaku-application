# ARCHITECTURE

## Overview

This is an **Application** repository (see the repository taxonomy in
[`PHILOSOPHY.md`](PHILOSOPHY.md)): the living system, built with DDD and Clean
Architecture.

## Layers

```
public/index.php          composition root + top-level routing
        │
        ▼
Interface/                controllers, CLI, presenters
        │
        ▼
Application               use cases
        │
        ▼
Domain                    entities, value objects, contracts, exceptions
        ▲
        │
Infrastructure            adapters (persistence, HTTP, environment)
```

Dependencies point inward: `Interface → Application → Domain`, and
`Infrastructure → Domain` (implementing the contracts).
