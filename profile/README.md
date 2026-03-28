# Luany

**A PHP framework built like a compiler, not a runtime interpreter — with an explicit request lifecycle and an AST-based template engine.**

Designed for developers who value predictability, performance, and clean architecture, Luany removes hidden magic and embraces a transparent, compiler-first approach to building modern web applications.

---

## Why Luany?

Most PHP frameworks rely heavily on runtime interpretation, string parsing, and implicit behavior.

Luany takes a different path:

- **Compiler-first architecture** — templates are parsed into AST and compiled into optimized PHP
- **Explicit request lifecycle** — every step from request to response is visible and controllable
- **Zero regex templating** — no fragile parsing, no hidden edge cases
- **Full CRUD in one command** — `luany make:feature Product name:string price:decimal` generates model, controller, migration, 4 views and routes
- **Zero-proxy live reload** — LDE connects browser directly to PHP; WebSocket carries only reload signals
- **Clean MVC foundation** — structured, predictable, and easy to scale

---

## Core Idea

> Build PHP applications the same way compilers work:
> parse → analyze → compile → execute

Instead of interpreting templates and logic at runtime, Luany compiles them ahead of time into efficient PHP code — making your application faster and more predictable.

---

## What Makes It Different?

| Feature | Traditional Frameworks | Luany |
|--------|------------------------|------|
| Template Engine | Regex / runtime parsing | AST + compilation |
| Request Lifecycle | Partially hidden | Fully explicit |
| CRUD Scaffolding | Multiple commands | One command, full feature |
| Live Reload | Proxy-based (BrowserSync) | Zero-proxy (LDE — WebSocket signals only) |
| Architecture | Convention + magic | Explicit + predictable |
| Performance | Runtime overhead | Precompiled views |

---

## Ecosystem

| Package | Description | Version |
|---------|-------------|---------|
| [luany/core](https://github.com/luany-ecosystem/luany-core) | HTTP Request/Response, Router, Middleware Pipeline | v1.0.0 |
| [luany/database](https://github.com/luany-ecosystem/luany-database) | PDO Connection, Query Builder, Active Record ORM, Migrations | v1.0.0 |
| [luany/framework](https://github.com/luany-ecosystem/luany-framework) | Application Container, Kernel, Service Providers, i18n | v1.0.0 |
| [luany/lte](https://github.com/luany-ecosystem/luany-lte) | AST-compiled template engine (`.lte` files) | v1.0.0 |
| [luany/cli](https://github.com/luany-ecosystem/luany-cli) | Command-line tool, scaffolding, migrations, LDE | v1.0.2 |
| [luany/luany](https://github.com/luany-ecosystem/luany) | Ready-to-use application skeleton | v1.1.0 |

### Tooling

- **[LTE for VS Code](https://github.com/luany-ecosystem/luany-lte-vscode)** — Syntax highlighting and tooling support for `.lte` template files.
- **[Benchmarks](https://github.com/luany-ecosystem/luany-benchmarks)** — Reproducible performance benchmarks and comparisons.

---

## Quick Start

```bash
# With Luany CLI (recommended)
composer global require luany/cli
luany new my-app
cd my-app

# Or directly via Composer
composer create-project luany/luany my-app
cd my-app

luany doctor
luany migrate

# Start dev server with live reload (LDE)
npm install
luany dev

# Or without live reload
luany serve
```

---

## Full CRUD in One Command

```bash
luany make:feature Product name:string price:decimal active:boolean
```

Generates: model · controller · migration · 4 LTE views · route file — ready to run in seconds.

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

## Documentation

[docs.luany.dev](https://docs.luany.dev) *(coming soon)*

---

## Philosophy

- Performance-first architecture with zero magic
- AST-driven templating — no regex parsing
- Explicit request lifecycle with clear middleware pipeline
- Full CRUD scaffolding — from zero to running feature in seconds
- Zero-proxy live reload — no BrowserSync loops, no session corruption

---

## Origin

Built in Angola 🇦🇴
Engineered for the global PHP community.

---

**License**: MIT | **PHP**: >= 8.2 | **Author**: António Ambrósio Ngola