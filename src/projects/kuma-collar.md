# Kuma Collar

> TODO: Picture or render of the collar
>
> TODO: Picture of Kuma

Kuma is my dog. He is a corgi. For walks at night, I would like to have an LED collar for him.

To make this happen, this will involve:

* A [WS2812b] strip for LEDs, capable of up to 1A of output
* A 18650 or 21700 battery cell, providing 3Ah-5Ah of power
* An nRF52840 MCU for control and communications, probably an [MS88SF2 module]
* A [LiPo stamp] for battery management and charging
* A custom PCB to hold all the parts
* A waterproof case of some kind, possibly cut acrylic
* [Aviation connectors] for:
    * USB data + power (4 pins)
    * WS2812b strip connection (3 pins)

[WS2812b]: ./../parts/leds/smart-leds.md
[LiPo stamp]: ./lipo-stamp.md
[Aviation connectors]: ./../parts/connectors/aviation.md
[MS88SF2 module]: ./../parts/modules/ms88sf2.md
