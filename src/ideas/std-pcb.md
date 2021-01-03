# Standard PCB Sizes

## Problem Statement

As a PCB designer, it is difficult to pick a "standard" size for designing hardware, where it will be possible to find off the shelf cases or accessories that will fit that board.

## Solution

Invent a new standard!

## Reference Material/Background

* IEC-602970-3 - [Eurocard standard]
    * I'm stealing the base card size
    * Based around a 100x160mm card
    * Typically used for test equipment
    * Also influnced [Eurorack] hardware
* ISO 216 - [Standard Paper Sizes]
    * I'm stealing the idea of "half sizes"
    * Every card is 1/2 the larger dimension of the next size up
    * ISO 216 keeps the same ratio - I don't.
* [Sick of Beige v1] - OSHW Board Sizes
    * Really similar approach
    * Based on the "golden ratio"
    * Also has an "alt" square format
    * Steal same spacing for mounting screws/edge keepout

[Eurocard standard]: https://en.wikipedia.org/wiki/Eurocard_%28printed_circuit_board%29
[Standard Paper Sizes]: https://en.wikipedia.org/wiki/ISO_216
[Sick of Beige v1]: http://dangerousprototypes.com/docs/Sick_of_Beige_standard_PCB_sizes_v1.0
[Eurorack]: https://en.wikipedia.org/wiki/Eurorack

## Standard rules

1. Start with a "base size" of 200x160mm
2. For each step, reduce the longest dimension by 1/2
3. For each size, there are four variants:
    1. AR: Full rectangle, corner mounted holes
    2. BR: Full rectangle, "plus" mounted holes
    3. AS: "Slim" rectangle, corner mounted holes
    4. BS: "Slim" rectangle, "plus" mounted holes
4. For all boards, mounting holes are M3 screws
    * 4x4mm from each corner
    * 3.2mm holes
    * TODO: What about small boards?
    * 6mm keepout around holes (diameter?)
    * 1.7mm edge keepout for case clearance

## Notes

* "Plus" mounted holes are for cases that have physical posts in the corners where the PCB must "keep out"

## Full case size listing

| Family | Variant | Full Name | Hole Location? | Board Shape | Width | Length | cm^2 |
| :--    | :--     | :--       | :--            | :--         | :--   | :--    | :--  |
| P0     | AR      | P0AR      | Corner Holes   | Regular     | 200   | 160    | 320  |
| P0     | AS      | P0AS      | Corner Holes   | Slim        | 200   | 80     | 160  |
| P0     | BR      | P0BR      | Plus Holes     | Regular     | 200   | 160    | 320  |
| P0     | BS      | P0BS      | Plus Holes     | Slim        | 200   | 80     | 160  |
| P1     | AR      | P1AR      | Corner Holes   | Regular     | 160   | 100    | 160  |
| P1     | AS      | P1AS      | Corner Holes   | Slim        | 160   | 50     | 80   |
| P1     | BR      | P1BR      | Plus Holes     | Regular     | 160   | 100    | 160  |
| P1     | BS      | P1BS      | Plus Holes     | Slim        | 160   | 50     | 80   |
| P2     | AR      | P2AR      | Corner Holes   | Regular     | 100   | 80     | 80   |
| P2     | AS      | P2AS      | Corner Holes   | Slim        | 100   | 40     | 40   |
| P2     | BR      | P2BR      | Plus Holes     | Regular     | 100   | 80     | 80   |
| P2     | BS      | P2BS      | Plus Holes     | Slim        | 100   | 40     | 40   |
| P3     | AR      | P3AR      | Corner Holes   | Regular     | 80    | 50     | 40   |
| P3     | AS      | P3AS      | Corner Holes   | Slim        | 80    | 25     | 20   |
| P3     | BR      | P3BR      | Plus Holes     | Regular     | 80    | 50     | 40   |
| P3     | BS      | P3BS      | Plus Holes     | Slim        | 80    | 25     | 20   |
| P4     | AR      | P4AR      | Corner Holes   | Regular     | 50    | 40     | 20   |
| P4     | AS      | P4AS      | Corner Holes   | Slim        | 50    | 20     | 10   |
| P4     | BR      | P4BR      | Plus Holes     | Regular     | 50    | 40     | 20   |
| P4     | BS      | P4BS      | Plus Holes     | Slim        | 50    | 20     | 10   |
| P5     | AR      | P5AR      | Corner Holes   | Regular     | 40    | 25     | 10   |
| P5     | AS      | P5AS      | Corner Holes   | Slim        | 40    | 12.5   | 5    |
| P5     | BR      | P5BR      | Plus Holes     | Regular     | 40    | 25     | 10   |
| P5     | BS      | P5BS      | Plus Holes     | Slim        | 40    | 12.5   | 5    |
| P6     | AR      | P6AR      | Corner Holes   | Regular     | 25    | 20     | 5    |
| P6     | AS      | P6AS      | Corner Holes   | Slim        | 25    | 10     | 2.5  |
| P6     | BR      | P6BR      | Plus Holes     | Regular     | 25    | 20     | 5    |
| P6     | BS      | P6BS      | Plus Holes     | Slim        | 25    | 10     | 2.5  |
| P7     | AR      | P7AR      | Corner Holes   | Regular     | 20    | 12.5   | 2.5  |
| P7     | AS      | P7AS      | Corner Holes   | Slim        | 20    | 6.25   | 1.25 |
| P7     | BR      | P7BR      | Plus Holes     | Regular     | 20    | 12.5   | 2.5  |
| P7     | BS      | P7BS      | Plus Holes     | Slim        | 20    | 6.25   | 1.25 |

## Unsorted

* https://twitter.com/bitshiftmask/status/1337100886066294786
