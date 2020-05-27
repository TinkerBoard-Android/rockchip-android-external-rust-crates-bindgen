[![crates.io](https://img.shields.io/crates/v/bindgen.svg)](https://crates.io/crates/bindgen)
[![docs.rs](https://docs.rs/bindgen/badge.svg)](https://docs.rs/bindgen/)

# `bindgen`

**`bindgen` automatically generates Rust FFI bindings to C (and some C++) libraries.**

For example, given the C header `doggo.h`:

```c
typedef struct Doggo {
    int many;
    char wow;
} Doggo;

void eleven_out_of_ten_majestic_af(Doggo* pupper);
```

`bindgen` produces Rust FFI code allowing you to call into the `doggo` library's
functions and use its types:

```rust
/* automatically generated by rust-bindgen */

#[repr(C)]
pub struct Doggo {
    pub many: ::std::os::raw::c_int,
    pub wow: ::std::os::raw::c_char,
}

extern "C" {
    pub fn eleven_out_of_ten_majestic_af(pupper: *mut Doggo);
}
```

## Users Guide

[📚 Read the `bindgen` users guide here! 📚](https://rust-lang.github.io/rust-bindgen)

## MSRV

The minimum supported Rust version is **1.34**.

No MSRV bump policy has been established yet, so MSRV may increase in any release.

## API Reference

[API reference documentation is on docs.rs](https://docs.rs/bindgen)

## Contributing

[See `CONTRIBUTING.md` for hacking on `bindgen`!](./CONTRIBUTING.md)
