
# ɴsɪ-sys

Auto-generated Rust bindings for *Illumination Research*’s *Nodal Scene
Interface* – ɴsɪ.

[![Build](https://github.com/virtualritz/nsi-sys/workflows/Build/badge.svg)](https://github.com/virtualritz/nsi-sys/actions)
[![Documentation](https://docs.rs/nsi-sys/badge.svg)](https://docs.rs/nsi-sys)
[![Crate](https://img.shields.io/crates/v/nsi-sys.svg)](https://crates.io/crates/nsi-sys)
[![Chat](https://badges.gitter.im/n-s-i/community.svg)](https://gitter.im/n-s-i/community)

You should not need to build this crate directly – unless you’re a
masochist who wants to use the C-API directly from Rust.

## Requirements

### Clang/Bindgen
The generator makes use of `bindgen`, which depends on *Clang*.
Instructions for installing `bindgen`'s dependencies for popular OSes
can be found in
[their documentation](https://rust-lang.github.io/rust-bindgen/requirements.html).

While `bindgen` may complain about a missing `llvm-config` binary it is
not actually required to build the crate. If you see a warning about
`llvm-config` and a failed build, it's likely that you're having a
different problem!

### Compile- vs. Runtime
The crate builds as-is, with default features.

However, at runtime this crate requires a library/renderer that
implements the ɴsɪ API to link against. Currently the only renderer
that does is [*3Delight*](https://www.3delight.com/).

If the feature flag `download_lib3delight` is enabled it fetches the
dynamic library version of *3Delight 2.1.2* for *Linux*, *macOS* and
*Windows*.
This is used as a fallback, to build against, if you do not have the
renderer installed on your system.

It is thus suggested that you
[download a 3Delight package](https://www.3delight.com/download) for
your platform & install it.
This will set the `DELIGHT` environment variable that the build script
is looking for to find a locally installed library to link against.

It will also install *3Delight Display* which you can render to,
progressively, as an alternative to writing images to disk.

> **_Note:_** The free version of 3Delight (no registration required) will render with up to 12 cores on your machine. For crazier projects you can use their cheap cloud rendering service that gives you access to unlimited CPU cores.

## High Level Bindings
There are high level Rust bindings for this API in the [ɴsɪ crate](https://crates.io/crates/nsi/).
