![Parity Ethereum](docs/logo-parity-ethereum.svg)

<h2 align="center">The Fastest and most Advanced Vitreo Client.</h2>

<p align="center"><strong><a href="https://github.com/vitreodev/parity-vitreo/releases/latest">» Download the latest release «</a></strong></p>

<p align="center"><a href="https://gitlab.parity.io/parity/parity-ethereum/commits/master" target="_blank"><img src="https://gitlab.parity.io/parity/parity-ethereum/badges/master/build.svg" /></a>
<a href="https://www.gnu.org/licenses/gpl-3.0.en.html" target="_blank"><img src="https://img.shields.io/badge/license-GPL%20v3-green.svg" /></a></p>

**Parity-Vitreo is Ported from Parity Technologies' Parity-Ethereum Codebase with the following features**:

- Clean, modular codebase for easy customisation
- Advanced CLI-based client
- Minimal memory and storage footprint
- Synchronise in hours, not days with Warp Sync
- Modular for light integration into your service or product

## Technical Overview

By default, Parity Vitreo runs a JSON-RPC HTTP server on port `:8545` and a Web-Sockets server on port `:8546`. This is fully configurable and supports a number of APIs.

Parity Vitreo's current beta-release is 0.1. You can build from source following the instructions below. Please, review the [CHANGELOG.md](CHANGELOG.md) for a list of all changes between different versions.

## Build Dependencies

Parity Vitreo requires **latest stable Rust version** to build.

We recommend installing Rust through [rustup](https://www.rustup.rs/). If you don't already have `rustup`, you can install it like this:

- Linux:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  Parity Vitreo also requires `cargo`, `perl`, `yasm`, `gcc`, `g++`, `libudev-dev`, `pkg-config`, `file`, `make`, and `cmake` packages to be installed. They can be installed with a single line:
	
  ```bash
  $ apt-get install cargo perl yasm gcc g++ libudev-dev pkg-config file make cmake
  ```

- OSX:
  ```bash
  $ curl https://sh.rustup.rs -sSf | sh
  ```

  `clang` is required. It comes with Xcode command line tools or can be installed with homebrew.

- Windows
  Make sure you have Visual Studio 2015 with C++ support installed. Next, download and run the `rustup` installer from
  https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe, start "VS2015 x64 Native Tools Command Prompt", and use the following command to install and set up the `msvc` toolchain:
  ```bash
  $ rustup default stable-x86_64-pc-windows-msvc
  ```
  Once you have `rustup` installed, then you need to install:
  * [Perl](https://www.perl.org)
  * [Yasm](https://yasm.tortall.net)

Make sure that these binaries are in your `PATH`. After that, you should be able to build Parity Vitreo from source.

## Build from Source Code

```bash
# Download Parity Vitreo code
$ git clone https://github.com/vitreodev/parity-vitreo
$ cd parity-vitreo
```
```bash
# build in release mode
$ cargo build --release --features final
```

This produces an executable in the `./target/release` subdirectory.

Note: if cargo fails to parse manifest try:

```bash
$ ~/.cargo/bin/cargo build --release
```

Note, when compiling a crate and you receive errors, it's in most cases your outdated version of Rust, or some of your crates have to be recompiled. Cleaning the repository will most likely solve the issue if you are on the latest stable version of Rust, try:

```bash
$ cargo clean
```

This always compiles the latest nightly builds. If you want to build stable or beta, do a

```bash
$ git checkout stable
```

or

```bash
$ git checkout beta
```
## Start Parity Vitreo

### Manually

To start Parity Vitreo manually, just run

```bash
$ ./target/release/parity
```

Then Parity Vitreo begins syncing the Vitreo blockchain.

### Using `systemd` service file

To start Parity Vitreo as a regular user using `systemd` init:

1. Copy `./scripts/parity.service` to your
`systemd` user directory (usually `~/.config/systemd/user`).
2. To configure Parity Vitreo, write a `/etc/parity/config.toml` config file, see [Configuring Parity Ethereum](https://paritytech.github.io/wiki/Configuring-Parity) for details.

## Parity Vitreo toolchain

In addition to the Parity Vitreo client, there are additional tools in this repository available:

- [evmbin](https://github.com/paritytech/parity-ethereum/blob/master/evmbin/) - EVM implementation for Parity Ethereum.
- [ethabi](https://github.com/paritytech/ethabi) - Parity Ethereum function calls encoding.
- [ethstore](https://github.com/paritytech/parity-ethereum/blob/master/ethstore/) - Parity Ethereum key management.
- [ethkey](https://github.com/paritytech/parity-ethereum/blob/master/ethkey/) - Parity Ethereum keys generator.
- [whisper](https://github.com/paritytech/parity-ethereum/blob/master/whisper/) - Implementation of Whisper-v2 PoC.
