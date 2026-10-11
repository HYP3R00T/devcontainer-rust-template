---
icon: lucide/rocket
---

# Getting started

## Requirements

Install Git, Docker Desktop, Visual Studio Code, and the Dev Containers extension. Start Docker Desktop before
opening the project. On Windows, use Docker Desktop with its WSL 2 backend.

## Create your repository

1. Select [Use this template](https://github.com/HYP3R00T/devcontainer-rust-template/generate) and create a repository.
2. Clone the new repository and open it in Visual Studio Code.
3. Run **Dev Containers: Reopen in Container** from the Command Palette.
4. Wait for setup to install the declared tools and configure Git hooks.
5. [Initialize a root package or Cargo workspace](rust-project.md).

## Tools and workflows

The Dev Container provides a Linux development environment across Windows, macOS, and Linux hosts.
Mise declares the project tools and provides tasks for running them.

- Rust uses the default profile, including rustfmt, Clippy, and local Rust docs.
- uv runs Python tools, including Commitizen and Zensical.
- The project entry script configures Git hooks and Commitizen.
- prek runs repository checks locally and in the pull-request quality gate.
- rumdl and ShellCheck check Markdown and shell scripts.
- Git attributes and ignore rules handle Rust source and build artifacts.
- Zensical publishes developer documentation.
- Dependabot updates GitHub Actions dependencies.
- Issue forms, contribution guidance, security reporting, and code ownership support repository maintenance.

## Verify the environment

```bash
mise doctor
mise ls --current
prek run --all-files
```

The template's CI checks repository files. Add Rust checks after initializing your Cargo project, following the
[Rust project setup guide](rust-project.md#add-rust-checks).

## Preview documentation

```bash
mise run docs
```

See the [contribution guide](https://github.com/HYP3R00T/devcontainer-rust-template/blob/main/CONTRIBUTING.md)
for the complete contribution workflow.
