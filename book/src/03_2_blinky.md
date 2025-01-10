# Blinky

Let's see how to create the iconic _Blinky_.


## Setup

✅ Go to `intro/blinky` directory.

✅ Open the prepared project skeleton in `intro/blinky`.

✅ Open the docs for this project with the following command:

```
cargo doc --open
```

`intro/blinky/examples/blinky.rs` contains the solution. You can run it with the following command:

```shell
cargo run --release --example blinky
```

## Exercise

On [ESP32-C3-DevKit-RUST-1] there is a regular [LED connected to GPIO 7]. If you use another board consult the data-sheet.

> Note that most of the development boards from Espressif today use an addressable LED which works differently and is beyond the scope of this book. In that case, you can also connect a regular LED to some of the free pins (and don't forget to add a resistor).

✅ Initiate the Io peripheral, and create a `led` variable from GPIO connected to the LED, using the
[`into_push_pull_output` function][into-push-pull-output].

Here we see that we can drive the pin `high`, `low`, or `toggle` it.

We also see that the HAL offers a way to delay execution.

✅ Initialize a Delay instance.

✅ Using the [`toggle()`][toggle] and [`delay_ms()`][delay-ms] methods, make the LED blink every 500 ms.


[ESP32-C3-DevKit-RUST-1]:  https://github.com/esp-rs/esp-rust-board
[LED connected to GPIO 7]: https://github.com/esp-rs/esp-rust-board#pin-layout
[into-push-pull-output]: https://docs.esp-rs.org/esp-hal/esp-hal/0.16.1/esp32c3/esp_hal/gpio/struct.GpioPin.html#method.into_push_pull_output
[toogle]: https://docs.rs/embedded-hal/0.2.7/embedded_hal/digital/v2/trait.ToggleableOutputPin.html#tymethod.toggle
[delay-ms]: https://docs.rs/embedded-hal/0.2.7/embedded_hal/blocking/delay/trait.DelayMs.html#tymethod.delay_ms
