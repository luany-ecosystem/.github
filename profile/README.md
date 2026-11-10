# Luany

**A PHP framework with an explicit request lifecycle and a compiled template engine — no hidden magic.**

Designed for developers who value predictability, performance, and clean architecture, Luany removes hidden magic and embraces a transparent, compiler-first approach to building modern web applications.

---

## Why Luany?

Most PHP frameworks rely heavily on runtime interpretation, string parsing, and implicit behavior.

Luany takes a different path:

- **Compiled templates** — LTE parses `.lte` files with a hand-written scanner and compiles them to cached PHP
- **Explicit request lifecycle** — every step from request to response is visible and controllable
- **Secure by default** — escaped output, CSRF protection, closed mass assignment, validated SQL identifiers
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
| Request Lifecycle | Partially hidden | Fully explicit |
| CRUD Scaffolding | Multiple commands | One command, full feature |
| Live Reload | Proxy-based (BrowserSync) | Zero-proxy (LDE — WebSocket signals only) |
| Architecture | Convention + magic | Explicit + predictable |

---

## Ecosystem

| Package | Description | Version |
|---------|-------------|---------|
| [luany/core](https://github.com/luany-ecosystem/luany-core) | HTTP Request/Response, Router, Middleware Pipeline | [![v](https://img.shields.io/packagist/v/luany/core)](https://packagist.org/packages/luany/core) |
| [luany/database](https://github.com/luany-ecosystem/luany-database) | PDO Connection, Query Builder, Active Record ORM, Migrations | [![v](https://img.shields.io/packagist/v/luany/database)](https://packagist.org/packages/luany/database) |
| [luany/framework](https://github.com/luany-ecosystem/luany-framework) | Application Container, Kernel, Service Providers, i18n | [![v](https://img.shields.io/packagist/v/luany/framework)](https://packagist.org/packages/luany/framework) |
| [luany/lte](https://github.com/luany-ecosystem/luany-lte) | Compiled template engine (`.lte` files) | [![v](https://img.shields.io/packagist/v/luany/lte)](https://packagist.org/packages/luany/lte) |
| [luany/cli](https://github.com/luany-ecosystem/luany-cli) | Command-line tool, scaffolding, migrations, LDE | [![v](https://img.shields.io/packagist/v/luany/cli)](https://packagist.org/packages/luany/cli) |
| [luany/luany](https://github.com/luany-ecosystem/luany) | Ready-to-use application skeleton | [![v](https://img.shields.io/packagist/v/luany/luany)](https://packagist.org/packages/luany/luany) |

### Tooling

- **[LTE for VS Code](https://github.com/luany-ecosystem/luany-lte-vscode)** — Syntax highlighting and tooling support for `.lte` template files.
- **Benchmarks** and a **Starter kit** (auth, dashboard) are planned — not yet published.

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
- Compiled templating with escaped output by default
- Explicit request lifecycle with clear middleware pipeline
- Full CRUD scaffolding — from zero to running feature in seconds
- Zero-proxy live reload — no BrowserSync loops, no session corruption

---

## Origin

Built in Angola 🇦🇴
Engineered for the global PHP community.

---

**License**: MIT | **PHP**: >= 8.2 | **Author**: António Ambrósio Ngola