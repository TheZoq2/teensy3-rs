# Rust on Teensy3

* `teensy3`: [![Crates.io](https://img.shields.io/crates/v/teensy3.svg)](https://crates.io/crates/teensy3)
* `teensy3-sys`: [![Crates.io](https://img.shields.io/crates/v/teensy3-sys.svg)](https://crates.io/crates/teensy3-sys)

[Documentation](https://docs.rs/crate/teensy3/)

This is a repo for development on the Teensy3 in Rust. This repo is bootstrapped
with Teensyduino bindings, generated by rust-bindgen.

## Getting Started

This crate is meant to be consumed by a binary for a PJRC Teensy 3.1 or 3.2. Support for Teensy 3.0, 3.5, and 3.6 boards is planned, but not implemented.

To use this crate, please see [this demo repo](https://github.com/jamesmunns/teensy3-rs-demo) which can be used as a template for your project.


## Package layout

* `teensy3-sys` - This crate contains the C/C++ code and the Rust bindings against them. All items are generally unsafe, and not idiomatic rust.
* `teensy3` - This crate contains any ergonomic wrappers around `teensy3-sys` components, as well as any pure rust reimplementations of other components. `teensy3-sys` is re-exported as `teensy3::bindings`.

## Dependencies

* A somewhat current Nightly Build of Rust (currently tested on `rustc 1.14.0-nightly (098d22845 2016-10-13)`)
* [Japaric's Xargo Tool](https://github.com/japaric/xargo) - used to cross compile libcore
* A somewhat current arm-none-eabi-gcc toolchain.
* Clang, see [rust-bindgen’s requirements](https://github.com/servo/rust-bindgen#requirements).

## Thanks, Citiations

This code is nearly entirely thanks to these resources:

* [PJRC's Teensyduino libraries](https://github.com/PaulStoffregen/cores) for the Teensy3, which are used as bindings.
* [Simon's teensy3-clock repo](https://github.com/SimonSapin/teensy-clock) for the rust main, build scripts, bindgen knowledge, et. al.
* [rust-bindgen](https://github.com/servo/rust-bindgen)

## License

Rust contributions are licensed under the MIT License.

**Please Note:** ASM, C, C++, and Linker Components of the `teensy3-sys` crate (a dependency of the `teensy3` crate) contain components licensed under the MIT License, PJRC's modified MIT License, and the LGPL v2.1. Please refer to individual components for more details.
