<p align="center">
<img src="https://raw.githubusercontent.com/rustic-rs/assets/main/logos/readme_header.png" height="400" />
</p>
<p align="center"><b>fast, encrypted, and deduplicated backups</b></p>

<p align="center">
<a href="https://crates.io/crates/rustic-rs"><img src="https://img.shields.io/crates/v/rustic-rs.svg" /></a>
<a href="https://docs.rs/rustic-rs/"><img src="https://img.shields.io/docsrs/rustic-rs?style=flat&amp;labelColor=1c1d42&amp;color=4f396a&amp;logo=Rust&amp;logoColor=white" /></a>
<a href="https://raw.githubusercontent.com/rustic-rs/rustic/main/"><img src="https://img.shields.io/badge/license-Apache2.0/MIT-blue.svg" /></a>
<a href="https://crates.io/crates/rustic-rs"><img src="https://img.shields.io/crates/d/rustic-rs.svg" /></a>
<a href="https://github.com/rustic-rs/rustic/actions/workflows/nightly.yml"><img src="https://github.com/rustic-rs/rustic/actions/workflows/nightly.yml/badge.svg" /></a>
<a href="https://github.com/rustic-rs/rustic/actions/workflows/release-image.yml"><img src="https://github.com/rustic-rs/rustic/actions/workflows/release-image.yml/badge.svg" /></a>
<p>

## About

`rustic` is a backup tool that provides fast, encrypted, deduplicated backups.

It reads and writes the [restic][1] repo format described in the
[design document][2] and can be used as a *restic* replacement in most cases.

It is implemented in [Rust](https://www.rust-lang.org/), a performant,
memory-efficient, and reliable cross-platform systems programming language.

Hence `rustic` supports all major operating systems (Linux, MacOs, *BSD), with
Windows support still being experimental.

### Stability

`rustic` currently is in **beta** state and misses regression tests. It is not
recommended to use it for production backups, yet.

## `rustic` Libraries

The `rustic` project is split into multiple crates:

- [rustic](https://crates.io/crates/rustic-rs) - the main binary
- [rustic-core](https://crates.io/crates/rustic_core) - the core library
- [rustic-backend](https://crates.io/crates/rustic_backend) - the library for
  supporting various backends

## Features

- Backup data is **deduplicated** and **encrypted**.
- Backup storage can be local or cloud storages, including cold storages.
- Allows multiple clients to **concurrently** access a backup repository using
  lock-free operations.
- Backups by default are append-only on the repository.
- The operations are robustly designed and can be **safely aborted** and
  **efficiently resumed**.
- Snapshot organization is possible by hostname, backup paths, label and tags.
  Also a rich set of metadata is saved with each snapshot.
- Retention policies and cleaning of old backups can be **highly customized**.
- Follow-up backups only process changed files, but still create a complete
  backup snapshot.
- In-place restore only modifies files which are changed.
- Uses config files for easy configuration of all every-day commands, see
  [example config files](/config/).

## Contact

You can ask questions in the [Discussions][3] or have a look at the
[FAQ](https://rustic.cli.rs/docs/FAQ.html).

| Contact       | Where?                                                                                                          |
| ------------- | --------------------------------------------------------------------------------------------------------------- |
| Issue Tracker | [GitHub Issues](https://github.com/rustic-rs/rustic/issues)                                                     |
| Discord       | [![Discord](https://dcbadge.vercel.app/api/server/WRUWENZnzQ?style=flat-square)](https://discord.gg/WRUWENZnzQ) |
| Discussions   | [GitHub Discussions](https://github.com/rustic-rs/rustic/discussions)                                           |

## Getting started

Please check our
[documentation](https://rustic.cli.rs/docs/getting_started.html) for more
information on how to get started.

## Installation

### From binaries

#### [cargo-binstall](https://crates.io/crates/cargo-binstall)

```bash
cargo binstall rustic-rs
```

#### Windows

##### [Scoop](https://scoop.sh/)

```bash
scoop install rustic
```

#### macOS

##### [Homebrew](https://brew.sh/)

```bash
brew install rustic
```

Or you can check out the
[releases](https://github.com/rustic-rs/rustic/releases).

Nightly binaries are available
[here](https://rustic.cli.rs/docs/nightly_builds.html).

### Docker

```bash
docker pull ghcr.io/rustic-rs/rustic
```

### From source

**Beware**: This installs the latest development version, which might be
unstable.

```bash
cargo install --git https://github.com/rustic-rs/rustic.git rustic-rs
```

### crates.io

```bash
cargo install --locked rustic-rs
```

## Differences to `restic`?

We have collected some improvements of `rustic` over `restic`
[here](https://rustic.cli.rs/docs/comparison-restic.html).

## Contributing

Tried rustic and not satisfied? Don't just walk away! You can help:

- You can report issues or suggest new features on our
  [Discord server](https://discord.gg/WRUWENZnzQ) or using
  [Github Issues](https://github.com/rustic-rs/rustic/issues/new/choose)!

Do you know how to code or got an idea for an improvement? Don't keep it to
yourself!

- [Contribute fixes](https://github.com/rustic-rs/rustic/contribute) or new
  features via a pull requests!

Please make sure, that you read the
[contribution guide](https://rustic.cli.rs/docs/contributing-to-rustic.html).

## Minimum Rust version policy

This crate's minimum supported `rustc` version is `1.80.0`.

The current policy is that the minimum Rust version required to use this crate
can be increased in minor version updates. For example, if `crate 1.0` requires
Rust 1.20.0, then `crate 1.0.z` for all values of `z` will also require Rust
1.20.0 or newer. However, `crate 1.y` for `y > 0` may require a newer minimum
version of Rust.

In general, this crate will be conservative with respect to the minimum
supported version of Rust.

## License

Licensed under either of:

- [Apache License, Version 2.0](./LICENSE-APACHE)
- [MIT license](./LICENSE-MIT)

at your option.

[//]: # (badges)
[//]: # (general links)
[1]: https://github.com/restic/restic
[2]: https://github.com/restic/restic/blob/master/doc/design.rst
[3]: https://github.com/rustic-rs/rustic/discussions
