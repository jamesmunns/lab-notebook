# BBQueue

BBQueue is a queue that aims to be a lock-free, performant, and misuse-resistant library for use with DMA on embedded systems. It is loosely based on [BipBuffers](https://www.codeproject.com/articles/3479/the-bip-buffer-the-circular-buffer-with-a-twist), as written by Simon Cooke.

In the near future, it will be rewritten to use the const-generic features that are stabilizing in Rust 1.50. This will mark the `1.0.0` release of bbqueue.

Useful links:

* [This blog post](https://ferrous-systems.com/blog/lock-free-ring-buffer/) explains the design and algorithm
* [This YouTube video](https://www.youtube.com/watch?v=ngTCf2cnGkY) is a guided walkthrough of the library
* [The library docs](https://docs.rs/bbqueue)
* [The project on GitHub](https://github.com/jamesmunns/bbqueue)
* A translation of this project in [Ada/Spark](https://github.com/Fabien-Chouteau/bbqueue-spark)

