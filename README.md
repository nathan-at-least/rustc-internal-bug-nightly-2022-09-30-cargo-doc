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

## in-repo cargo and rustc versions

Inside this repo directory, which contains `rust-toolchain.toml`, I have:

```
$ cargo --version --verbose
cargo 1.66.0-nightly (f5fed93ba 2022-09-27)
release: 1.66.0-nightly
commit-hash: f5fed93ba24607980647962c59863bbabb03ce14
commit-date: 2022-09-27
host: x86_64-unknown-linux-gnu
libgit2: 1.5.0 (sys:0.15.0 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1q)
os: Debian 11 (bullseye) [64-bit]
```

```
$ rustc --version --verbose
rustc 1.66.0-nightly (9c56d9d6f 2022-09-29)
binary: rustc
commit-hash: 9c56d9d6fec6262bbb1549cfe466a812ae2c6523
commit-date: 2022-09-29
host: x86_64-unknown-linux-gnu
release: 1.66.0-nightly
LLVM version: 15.0.0
```


## base user cargo and rustc versions

Outside of the repo without a `rust-toolchain.toml`, I have:

```
$ cargo --version --verbose
cargo 1.63.0 (fd9c4297c 2022-07-01)
release: 1.63.0
commit-hash: fd9c4297ccbee36d39e9a79067edab0b614edb5a
commit-date: 2022-07-01
host: x86_64-unknown-linux-gnu
libgit2: 1.4.2 (sys:0.14.2 vendored)
libcurl: 7.83.1-DEV (sys:0.4.55+curl-7.83.1 vendored ssl:OpenSSL/1.1.1n)
os: Debian 11 (bullseye) [64-bit]
```

```
$ rustc --version --verbose
rustc 1.63.0 (4b91a6ea7 2022-08-08)
binary: rustc
commit-hash: 4b91a6ea7258a947e59c6522cd5898e7c0a6a88f
commit-date: 2022-08-08
host: x86_64-unknown-linux-gnu
release: 1.63.0
LLVM version: 14.0.5
```
