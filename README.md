# Repro case for rustdoc crash

Steps to reproduce:

Nightly:
```shell script
rustup toolchain install nightly-2019-08-22
cargo +nightly-2019-08-22 clean
cargo +nightly-2019-08-22 doc
```

Stable (1.37.0), with RUSTC_BOOTSTRAP=1:
```shell script
rustup toolchain install 1.37.0
cargo +1.37.0 clean
RUSTC_BOOTSTRAP=1 cargo +1.37.0 doc
```

Stable (1.37.0), without RUSTC_BOOTSTRAP=1, does not reproduce:
```shell script
rustup toolchain install 1.37.0
cargo +1.37.0 clean
cargo +1.37.0 doc
```