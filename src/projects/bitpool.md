# bitpool

`bitpool` is intended to be a lightweight and lock-free allocator for embedded systems.

It aims to support all of the following use cases:

* As a global `static` memory pool (without language support)
* As an implementor of the `global_alloc`, allowing for use with the `alloc` crate
* As an implementor of whatever future "local allocator" traits are provided, allowing it to be used as a custom allocator for collections

bitpool uses a 32-bit word as a tree of booleans which express the ability to break a page into blocks ranging up to 5 power-of-two allocations.

For example, when using a 1024 byte "page", you could have any combination of the following blocks allocatable:

* 1x 1024 byte block
* 2x 512 byte blocks
* 4x 256 byte blocks
* 8x 128 byte blocks
* 16x 64 byte blocks

Because a bit is used for each "tier" of blocks, this uses 31 bits of metadata per block `(1 + 2 + 4 + 8 + 16) = 31`. This allows for atomic CAS operations on each block metadata word.

In the future, it should be possible for users to choose any power-of-two as the page size, meaning you could have two (or more) pools that cover a wider range, e.g.:

* Pool 1 (small): 1024-64 byte allocations
* Pool 2 (medium): 16KiB-2KiB allocations
* Pool 3 (large): 512KiB-32KiB allocations

See [the github repo](https://github.com/jamesmunns/bitpool) for more information.
