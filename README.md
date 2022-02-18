
# `nsi-sys`

[![Build](https://github.com/virtualritz/nsi-sys/workflows/Build/badge.svg)](https://github.com/virtualritz/nsi-sys/actions)
[![Documentation](https://docs.rs/nsi-sys/badge.svg)](https://docs.rs/nsi-sys)
[![Crate](https://img.shields.io/crates/v/nsi-sys.svg)](https://crates.io/crates/nsi-sys)
[![Chat](https://badges.gitter.im/n-s-i/community.svg)](https://gitter.im/n-s-i/community)
![Maintenance](https://img.shields.io/badge/maintenance-passively--maintained-yellowgreen.svg)

Auto-generated Rust bindings for *Illumination Research*’s *Nodal
Scene Interface* – ɴsɪ.

You should not need to use this crate directly except for two
reasons. You are likely either:
* a masochist who wants to use the C-API directly from Rust.
* writing a renderer that exposes an ɴsɪ C-API.

## High Level Bindings

There are high level Rust bindings for this API in the
[ɴsɪ crate](https://crates.io/crates/nsi/).

## Compile- vs. Runtime

The crate builds as-is, with default features.

However, at runtime this crate requires a library/renderer that
implements the ɴsɪ C-API to link against. Currently the only
renderer that does is [*3Delight*](https://www.3delight.com/).

## Features

* `download_lib3delight` – Fetches the dynamic library version of
  *3Delight 2.1.2* for *Linux*, *macOS* or *Windows*.

  This can be used as a fallback, to build against, if you do not
  have the renderer installed on your system. But it is an old
  version of 3Delight and foremost a CI feature.

  It is instead suggested that you
  [download a *3Delight* package](https://www.3delight.com/download)
  for your platform & install it. This will set the `DELIGHT`
  environment variable that the build script is looking for to find
  a locally installed library to link against. Free version renders
  with up to 12 cores.

  This will also install *3Delight Display* which you can render
  to, progressively – useful for debugging.

* `link_lib3delight` – Links against the dynamic library version of
   3Delight. Requires the `DELIGHT` environment variable to be set.

* `omit_functions` – Omit generating bindings for the API's
   functions. This is for the casewhere you want to expose your own
   C-API hooks from your renderer.

## License

Apache-2.0 OR BSD-3-Clause OR MIT OR Zlib

at your option.
