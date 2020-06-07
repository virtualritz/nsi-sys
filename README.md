
# ɴsɪ-sys

Auto-generated Rust bindings for Illumination Research’s Nodal Scene Interface – ɴsɪ.

[![CI](https://github.com/virtualritz/nsi-sys/workflows/Rust/badge.svg)](https://github.com/virtualritz/nsi-sys/actions)
[![Documentation](https://docs.rs/nsi-sys/badge.svg)](https://docs.rs/nsi-sys)
[![Crate](https://img.shields.io/crates/v/nsi-sys.svg)](https://crates.io/crates/nsi-sys)
[![Chat](https://badges.gitter.im/n-s-i/community.svg)](https://gitter.im/n-s-i/community)

## Dependencies

This crate requires a library/renderer that implements the ɴsɪ API to link against. Currently the only renderer that does is [3Delight](https://www.3delight.com/).

The crate ships with the `nsi.h` header & dynamic library version of 3Delight 2.1.2 for Linux, macOS and Windows. This is used as a fallback, to build against, if you do not have the renderer installed on your system.

It is thus suggested that you [download a 3Delight package](https://www.3delight.com/download) for your platform & install it.
This will set the `DELIGHT` environment variable that the build script is looking for to find locally installed headers and the library to link against.

It will also install 3Delight Display which you can render to, progressively, as an alternative to writing images to disk.

> **_Note:_** The free version of 3Delight (no registration required) will render with up to 12 cores on your machine. For crazier projects you can use their cheap cloud rendering service that gives you access to unlimited CPU cores.

## Building

You should not need to build this crate directly unless you’re a masochist who wants to use the C-API directly from Rust.

## High Level Bindings

There are high level Rust bindings for this API in the [NSI repository](https://github.com/virtualritz/nsi).
