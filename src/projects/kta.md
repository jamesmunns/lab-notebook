# Knurling Test Adapter

> Note: Add picture or render of the breakout board

This is intended to be used as part of Hardware in the Loop testing. The idea is the ability to write host-based "integration tests" that exercise the behavior of a Unit Under Test (UUT) by mocking the outside world, or serving as a data Sink or Source for instrumentation commands or logging.

See [HIL Testing Theory](./../ideas/hil-testing.md) for more design and concept details.

It is currently a breakout board for the [Black Pill], based on the STM32F411. The breakout board adds:

* Dual RS-485 channels
* RJ-45 connectors for daisy-chaining power and RS-485
* A WS2812B LED for status
* PMOD breakouts for:
    * GPIO
    * I2C
    * SPI
    * UARTs

In the future, the hope is to donate this project to the [Knurling-rs project](https://knurling.ferrous-systems.com/).
