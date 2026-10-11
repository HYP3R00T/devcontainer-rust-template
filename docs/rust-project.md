---
icon: lucide/terminal
---

# Initialize your Rust project

The template has no Cargo manifest or starter package. Choose the structure your project needs.
`mise.toml` requests the latest stable Rust with the default profile, which includes rustfmt, Clippy, and local Rust docs.
`mise.lock` records the resolved version for consistent local and CI installs. Run `mise upgrade rust` to update Rust,
then verify your project and commit the lockfile change.

## Root package

From the repository root, choose one:

```bash
# Binary package (CLI or application).
cargo init --bin --name my-app .

# Library package.
cargo init --lib --name my-lib .
```

Cargo creates a root `Cargo.toml` and `src/` directory. Run a binary with `cargo run`, or test either package type
with `cargo test`. Set `license = "MIT"` in the package manifest if retaining the template's license,
and `publish = false` for a package that should stay private.

## Cargo workspace

First create the initial package from the repository root:

```bash
cargo new --bin crates/my-app
```

For a library instead, use `cargo new --lib crates/my-lib`.
Then manually create a root `Cargo.toml` containing:

```toml
[workspace]
members = ["crates/*"]
resolver = "3"

[workspace.package]
edition = "2024"
license = "MIT"
```

In the initial package's `Cargo.toml`, replace its `edition` entry with `edition.workspace = true`
and add `license.workspace = true`. Set `publish = false` for packages that should stay private.
Keep at least one package in the workspace.

`crates/` is a directory convention, not the workspace's name. The root manifest defines the workspace.
Add more packages with `cargo new --bin crates/my-cli` or `cargo new --lib crates/my-lib`.
The `crates/*` pattern includes them automatically, so you don't need to edit the root manifest for each addition.
Check each package's manifest for the shared edition and license settings.

Run or test a package by the name in its `Cargo.toml`:

```bash
cargo run -p my-app
cargo test -p my-lib
```

Workspaces share a root `Cargo.lock` and `target/` directory.

## Add Rust checks

After initializing either structure, run `cargo generate-lockfile` and commit `Cargo.lock`.
Add this task to `mise.toml`:

```toml
[tasks.check]
description = "Check Rust formatting, lints, and tests"
run = [
  "cargo fmt --all -- --check",
  "cargo clippy --workspace --all-targets --locked -- -D warnings",
  "cargo test --workspace --locked",
]
```

Run `mise run check` locally. These commands work for a root package or a workspace.
Add a Rust job to `.github/workflows/ci.yml` that installs Rust through `jdx/mise-action@v4`
with `install_args: rust` and runs `mise run check`. The template's CI runs repository checks until you add that job.
Commit lockfile changes after adding packages or dependencies, and add tests for your application's behavior.
