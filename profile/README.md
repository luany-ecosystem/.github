# Luany

**AST-compiled PHP MVC framework with an explicit request lifecycle and zero-regex template engine.**

Designed with a compiler-first mindset, Luany focuses on predictable behavior, clean abstractions, and minimal overhead.

---

## Ecosystem

| Package | Description | Version |
|---------|-------------|---------|
| [luany/core](https://github.com/luany-ecosystem/luany-core) | HTTP Request/Response, Router, Middleware Pipeline | v0.2.4 |
| [luany/database](https://github.com/luany-ecosystem/luany-database) | PDO Connection, Query Builder, Active Record ORM, Migrations | v0.1.3 |
| [luany/framework](https://github.com/luany-ecosystem/luany-framework) | Application Container, Kernel, Service Providers, i18n | v0.3.1 |
| [luany/lte](https://github.com/luany-ecosystem/luany-lte) | AST-compiled template engine (`.lte` files) | v0.2.x |
| [luany/cli](https://github.com/luany-ecosystem/luany-cli) | Command-line tool, scaffolding, migrations | v0.2.2 |
| [luany/luany](https://github.com/luany-ecosystem/luany) | Ready-to-use application skeleton | — |

### Tooling

- **[LTE for VS Code](https://github.com/luany-ecosystem/luany-lte-vscode)** — Syntax highlighting and tooling support for `.lte` template files.
- **[Benchmarks](https://github.com/luany-ecosystem/luany-benchmarks)** — Reproducible performance benchmarks and comparisons.

---

## Quick Start

```bash
composer create-project luany/luany my-app
cd my-app
luany key:generate
luany serve
```

---

## Architecture

```
Browser → public/index.php → bootstrap/app.php → Kernel::boot()
    → Kernel::handle(Request) → Pipeline → Middleware → Router → Controller → Response
```

### Dependency Graph

```
luany/luany (skeleton)
├── luany/framework
│   ├── luany/core
│   └── luany/lte
├── luany/database
└── luany/cli (dev)
```

---

## Philosophy

- Performance-first architecture with zero magic
- AST-driven templating — no regex parsing
- Explicit request lifecycle with clear middleware pipeline
- Clean MVC design built for simplicity and long-term scalability

---

## Origin

Built in Angola.
Engineered for the global PHP community.

---

**License**: MIT | **PHP**: >= 8.1 | **Author**: António Ambrósio Ngola
