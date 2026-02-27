# preview-anything

Zero-config CLI to detect, run, and preview any JavaScript project.

Works with frontend apps, backend APIs, static sites, and full-stack projects — locally or inside a Docker sandbox.

---

## Why preview-anything?

Cloned a repo and don’t know how to run it?

Generated code from AI and want an instant preview?

Building a dev tool that needs automatic project execution?

Instead of figuring out scripts, ports, and environments manually:

```bash
npx preview-anything ./project
```

That’s it.

---

## Features

- Automatic framework detection
- Dependency installation
- Smart port resolution
- Process lifecycle management
- Optional Docker sandbox mode
- Works with frontend, backend, and static projects
- Clean log streaming
- Graceful shutdown handling

---

## Installation

Run without installing:

```bash
npx preview-anything
```

Or install globally:

```bash
npm install -g preview-anything
```

---

## Usage

Preview current directory:

```bash
preview-anything
```

Preview specific folder:

```bash
preview-anything ./my-app
```

Run in sandbox mode:

```bash
preview-anything ./my-app --sandbox
```

Specify port:

```bash
preview-anything --port 4000
```

Skip dependency installation:

```bash
preview-anything --no-install
```

Enable verbose logging:

```bash
preview-anything --verbose
```

---

## Supported Frameworks (Phase 1)

- Next.js
- Vite (React, Vue)
- Create React App
- Express
- Node servers
- Static HTML sites

Detection is automatic. No configuration required.

---

## How It Works

1. Analyzes the project structure
2. Detects framework and scripts
3. Generates an execution plan
4. Installs dependencies (if needed)
5. Resolves an available port
6. Starts the server
7. Streams logs and opens preview

Optional sandbox mode runs the project inside a temporary Docker container with resource limits.

---

## Sandbox Mode

Use Docker for isolated execution:

```bash
preview-anything --sandbox
```

Sandbox mode provides:

- CPU limits
- Memory limits
- Timeout auto-termination
- Isolated filesystem
- Automatic cleanup

Useful for:

- AI code generation platforms
- Multi-tenant preview systems
- Secure execution environments

---

## Example Workflow

Cloning and previewing a project:

```bash
git clone https://github.com/example/project.git
cd project
npx preview-anything
```

Previewing generated output:

```bash
generate-app ./output
npx preview-anything ./output
```

---

## CLI Options

| Option | Description |
|--------|------------|
| `--sandbox` | Run inside Docker |
| `--port <number>` | Override default port |
| `--timeout <ms>` | Auto-kill after timeout |
| `--no-install` | Skip dependency installation |
| `--verbose` | Show detailed logs |

---

## Architecture Overview

preview-anything is structured into modular layers:

- CLI Layer
- Project Analyzer
- Framework Resolver
- Execution Planner
- Runtime Engine (Local / Docker)
- Port Manager
- Process Supervisor

This separation allows it to scale from a simple CLI tool to an infrastructure layer for larger systems.

---

## Use Cases

- AI website builders
- Developer onboarding
- Internal tooling
- Preview environments
- Code playground platforms
- Continuous integration workflows

---

## Roadmap

- Multi-service detection (frontend + backend)
- Unified proxy routing
- Shareable preview URLs
- GitHub PR integration
- Cloud preview mode
- Plugin system for custom frameworks

---

## Philosophy

preview-anything is designed to:

- Require zero configuration
- Make reasonable assumptions
- Fail gracefully
- Work consistently across projects
- Be infrastructure-ready

---

## Contributing

Contributions are welcome.  
Please open issues for framework detection improvements or runtime enhancements.

---

## License

MIT