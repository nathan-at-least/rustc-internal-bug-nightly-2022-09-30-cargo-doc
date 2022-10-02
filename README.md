`rustc` bug reproduction, filed as [rust issue #102603](https://github.com/rust-lang/rust/issues/102603).

To trigger run:

```
cargo doc
```

# repro toolchain

## rustup

```
$ rustup --version
rustup 1.25.1 (bb60b1e89 2022-07-12)
info: This is the version for the rustup toolchain manager, not the rustc compiler.
info: The currently active `rustc` version is `rustc 1.66.0-nightly (9c56d9d6f 2022-09-29)`
```

## cargo inside repo

Inside this repo directory, which contains `rust-toolchain.toml`, I have:

```
$ cargo --version
cargo 1.66.0-nightly (f5fed93ba 2022-09-27)
```

## cargo as typical user

Outside of the repo without a `rust-toolchain.toml`, I have:

```
$ cargo --version
cargo 1.63.0 (fd9c4297c 2022-07-01)
```
