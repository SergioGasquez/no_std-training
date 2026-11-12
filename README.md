# no_std training

[![CI](https://github.com/esp-rs/no_std-training/actions/workflows/ci.yml/badge.svg)](https://github.com/esp-rs/no_std-training/actions/workflows/ci.yml)

This repository contains training material for learning embedded Rust with `no_std` on the Espressif ESP32-C3. Over the course of the training you build a data logger that reads a temperature and humidity sensor, connects to Wi-Fi, publishes measurements to an MQTT broker, receives Wi-Fi credentials through a provisioning portal, and updates itself over the air.

We suggest you start by reading [the book](https://docs.espressif.com/projects/rust/no_std-training/).

## Contents

- [`training/`](./training): Source of the book.
- [`project/`](./project): The application at the end of each chapter:
  - [`part1`](./project/part1): Reading sensor data.
  - [`part2`](./project/part2): Wi-Fi connectivity.
  - [`part3`](./project/part3): Publishing data to an MQTT broker.
  - [`part4`](./project/part4): Wi-Fi provisioning.
  - [`part5`](./project/part5): Over-the-air updates.
- [`xtask/`](./xtask): Host tools used during the training:
  - `cargo xtask mqtt-server`: Local MQTT broker that prints received measurements.
  - `cargo xtask http-server`: Local HTTP server that prints sensor payloads.
  - `cargo xtask ota-server --firmware <path>`: Local HTTP server that serves a firmware image for OTA updates.

## Building the Book

The book is built with [mdBook] and the [`mdbook-mermaid`] and [`mdbook-shiftinclude`] preprocessors:

```shell
cargo install mdbook mdbook-mermaid mdbook-shiftinclude --locked
mdbook serve --open
```

[mdBook]: https://github.com/rust-lang/mdBook
[`mdbook-mermaid`]: https://github.com/badboy/mdbook-mermaid
[`mdbook-shiftinclude`]: https://github.com/daviddrysdale/mdbook-shiftinclude

## License

The code is licensed under either of [Apache License, Version 2.0](./LICENSE-APACHE) or [MIT License](./LICENSE-MIT) at your option. The written prose, pictures and diagrams are licensed under [CC BY-SA 4.0](./LICENSE-CC-BY-SA).
