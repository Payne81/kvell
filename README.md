***

* [Docs[TODO]](https://docs.rs/kvell)
* [Cargo package](https://crates.io/crates/kvell)

## Summary

A Fast Persistent Key-Value Store base on [KVell: the Design and Implementation of a
Fast Persistent Key-Value Store](https://dl.acm.org/doi/pdf/10.1145/3341301.3359628).

## Features

* Shared-nothing: all data structures are partitioned among cores so that each core can operate almost entirely without any synchronization.
* Items are not sorted on disk: An in-memory sorted index is maintained per partition for efficient scans.
* No attempt is made to force sequential access, but I/O operations are batched to reduce the number of costly system calls. Batching furthermore provides control over the length of the device queues, making it possible to simultaneously achieve low latency and high throughput.
* No commit log:  updates are acknowledged only after they have been persisted at their final location on disk.


<!-- ## Example -->


## License

* MIT license ([LICENSE-MIT](./LICENSE-MIT) or http://opensource.org/licenses/MIT).

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in kvell by you, shall be licensed as MIT, without any additional terms or conditions.
