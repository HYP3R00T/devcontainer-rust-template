<!-- rumdl-disable MD041 -->

<div align="center">

# DevContainer Rust Template

A minimal, reusable foundation for Rust projects with consistent development environments and maintainable workflows.

[Documentation](https://hyp3r00t.github.io/devcontainer-rust-template/) · [Use this template](https://github.com/HYP3R00T/devcontainer-rust-template/generate) · [Contributing](CONTRIBUTING.md)

[![Quality Gate](https://img.shields.io/github/actions/workflow/status/HYP3R00T/devcontainer-rust-template/ci.yml?branch=main&style=for-the-badge&label=Quality%20Gate&logo=githubactions)](https://github.com/HYP3R00T/devcontainer-rust-template/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/github/license/HYP3R00T/devcontainer-rust-template?style=for-the-badge&label=License)](LICENSE)

</div>

<!-- Add a project screenshot or demonstration here. -->

## About

This repository provides a starting point for Rust projects that need a predictable Linux development environment across Windows, macOS, and Linux hosts. The Dev Container supplies the environment, while Mise provides a shared interface for installing and running project tools.

The template includes repository checks, contribution guidance, documentation publishing, and Git attributes and ignore rules for Rust files. A Rust toolchain and Cargo project are not configured yet; add them along with the tests and tasks your project needs.

## Features

- Reproducible development through a Docker-based Dev Container.
- A Bash project entry script that configures Git hooks and Commitizen.
- Tool and task management with [Mise](https://mise.jdx.dev/).
- Local Git hooks and repository checks powered by [prek](https://prek.j178.dev/).
- A pull-request quality gate that runs the same checks as local development.
- Structured issue forms, contribution guidance, security reporting, and code ownership.
- Rust-specific Git attributes and ignore rules for build output and tool artifacts.
- Developer documentation published with [Zensical](https://zensical.org/).
- Automated GitHub Actions dependency updates through Dependabot.

## Use this template

1. Select [**Use this template**](https://github.com/HYP3R00T/devcontainer-rust-template/generate) and create a repository.
2. Clone the new repository and open it in Visual Studio Code with Docker running and the Dev Containers extension installed.
3. Run **Dev Containers: Reopen in Container** from the Command Palette.
4. Wait for the setup to install the declared tools and configure the Git hooks.
5. Configure a Rust toolchain, initialize your Cargo project, and add its dependencies, tests, and checks.

For environment requirements and verification commands, read [CONTRIBUTING.md](CONTRIBUTING.md).

## Contributing

Contributions are welcome when they are focused, understandable, and maintainable. Read [CONTRIBUTING.md](CONTRIBUTING.md) before proposing a change.

## License

This project is available under the [MIT License](LICENSE).

<div align="center">

Developed with ❤️ by [HYP3R00T](https://github.com/HYP3R00T)

</div>
