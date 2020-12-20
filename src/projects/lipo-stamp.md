# LiPo Stamp

![LiPo Stamp Render](https://raw.githubusercontent.com/jamesmunns/lipo-stamp/main/assets/lipo-stamp.png)

The LiPo Stamp is a small sized, general purpose LiPo charge controller with power path and a 3v3 regulator. Currently the targeted size is 0.7" by 0.7", or just under 18mm square. It is intended to be used with single cell 18650, 21700, pack, or similar batteries.

I intend to use this in projects such as [Kuma's Collar](./kuma-collar.md).

## Features

* TP4056 Charge Controller
    * 500mA charging current
    * Low voltage trickle charging
* Over/Under-voltage Protection
    * AP9101CK6 + FS8205
    * Disables battery on over/under charge
* Power Path
    * Provides power via USB when connected
    * 500mA max output (USB or Battery)
* Switchable 3v3 Regulator
    * Default off
    * 100mA+ output
* Resettable Polyfuse
    * For high current, direct battery applications (e.g. LEDs)
    * Max 2A continuous output

The main project page for the LiPo Stamp is [hosted on GitHub](https://github.com/jamesmunns/lipo-stamp).
