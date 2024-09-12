# Simple-kernel

## Dependencies:

**cargo-binutils**

```bash
$ rustup component add llvm-tools

$ cargo install cargo-binutils --vers 0.3.3

$ cargo size --version
cargo-size 0.3.3
```

**cargo-embed**

In order to install cargo-embed, first install its [prerequisites](https://probe.rs/docs/getting-started/installation/) (note: these instructions are part of the more general [`probe-rs`](https://probe.rs/) embedded debugging toolkit). Then install it with cargo:

```bash
$ cargo install probe-rs-tools --vers 0.24.0

$ cargo embed --version
cargo-embed 0.24.0 (git commit: crates.io)
```

**Linux**

```bash
sudo apt-get install \
  gdb-multiarch \
  minicom
```

```bash
rustup override set nightly
cargo install bootimage
```

## Getting started

```bash
cargo bootimage
qemu-system-x86_64 -drive format=raw,file=target/x86-unknown-bare_metal/debug/bootimage-simple-kernel.bin
```