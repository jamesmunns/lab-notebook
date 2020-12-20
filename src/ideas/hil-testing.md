# HIL Testing Theory

I think that Hardware in the Loop testing breaks down into three "dimensions", or aspects that represents some aspect of an individual test or test case. These include:

* **Interfaces** - or how you interact with your unit under test
* **Behaviors** - or how your test adapter behaves over one or more **Interfaces**
* **Paradigms** - or how your test is structured between the testing host and the testing adapter

IMO, every test will be some combination of all three of these dimensions.

This list discusses **hosts**, or the PC orchestrating the test cases, the **adapter**, which manages real time communications and simulation, and the **unit under test**, the device that is being tested.

## Dimensions

* **Interfaces**
    * GPIOs
    * SPI
    * I2C
    * UART
    * ADCs
    * DACs/PWM
    * I2S
    * CANBus
    * RS-485
    * Long tail of domain specific interfaces/protocols
* **Behaviors**
    * Immediate Read (one value)
    * Immediate Write (one value)
    * Stream In (sniffing)
    * Stream Out (dumping)
    * React/Response (potentially chained)
        * e.g. GPIO goes low, send UART message
    * Table/Register Based
        * e.g. SPI/I2C
    * Sequencing/Timing?
    * Controlling External Tools, e.g.
        * Power Supply
        * Relay
        * Current sensor
        * Expansion Boards/"Hats"/"Shields"
* **Paradigms**
    * Adapter: 0% automated; Host: 100% automated - Raspberry Pi use cases
        * Immediate "host side" controls
        * Assume 10-100ms Round Trip Latency
    * Adapter: 33% automated; Host: 66% automated (IFTTT-lite) - Arduino use cases
        * Host: Preloads specific response/trigger behavior
        * Adapter: Limited number of trigger responses
        * 0ms latency for "automated" tasks, 10-100ms for Roundtrip
    * Adapter: 66% automated; Host: 33% automated (Full sequencer)
        * Host: Set up specific sequences
        * Adapter: Can hold up to N actions, triggered by M conditions
    * Adapter: 100% automated; Host: 0% automated
        * Adapter has a full scripting environment (WASM, Python, 'pre-compiled')
        * Host: Just loads scripts and executes test cases
