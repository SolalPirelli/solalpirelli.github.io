---
title: A Simpler and Faster NIC Driver Model for Network Functions
excerpt: Rethinking network card drivers for a constrained app model
date: 2020-11-04
venue: OSDI '20
authors: S. Pirelli, G. Candea
artifact: https://github.com/dslab-epfl/tinynf
video: https://youtu.be/zKJIY4vbBDA
doi: https://www.usenix.org/conference/osdi20/presentation/pirelli
---

My first conference first-author paper! This one was kind of a long shot; I have tweeted about how [maintaining a good artifact](https://twitter.com/SolalPirelli/status/1590720322697039873) was key to its success.


## Problem

Automatically verified network functions couldn't reach the throughput of unverified ones because _batching_ was necessary for high throughput.
More precisely, instead of reading packets from the network card one by one, batched drivers read as many packets as they can up to a configurable limit.
This amortizes overheads such as writing to network card registers, yet makes automated verification infeasible due to the exponential explosion of paths.


## Hypothesis

Batching is a way to get information about load, not the only way to get high throughput.
Instead of obtaining accurate information about load by looking at future packets, predicting load based on past packets is enough.
Thus, we can have high throughput while processing packets one by one.


## Results

It works!
Our "TinyNF" driver model for network functions processes packets one by one, and decides when to write to the network card's transmission register based on estimated load.
Specifically, if there are no packets waiting to be processed, it's a good time to transmit the packets that have finished processing;
and if there are too many processed packets awaiting transmissions, we should transmit them regardless of load.

There are additional interesting constraints and implementation details described in the paper, such as synchronizing the states of multiple output devices to minimize the work the driver has to do.
The driver is implemented in C without any language extensions, vectorization, or other fancy features, which makes it easy to study and port to other languages.

An unexpected result is that our driver outperforms DPDK's heavily-optimized general-purpose driver _except for no-op network functions_, which are the kind usually used in driver performance benchmarks.
This can be explained by looking at CPU metrics such as cache misses: it turns out DPDK takes most CPU resources for itself, which is fine when the network function does nothing,
but starts to conflict with the software it is supposed to help when that software also wants to use resources.


## Limitations

Our driver model is designed for functions that process one packet at a time, optionally modify its contents, and either forward or drop it.
Keeping packets around, such as to reorder out-of-order messages, would require copying and probably outweigh the performance gains.


## Lessons Learned

**Question common wisdom!**
This project was driven by me finding it weird that "batching is necessary" was apparently seen as an obvious fact that did not need proving.
Turns out in some cases it isn't necessary!

**Benchmark real use cases.**
DPDK, at least as of writing this paper, was benchmarked with the completely unrealistic scenario of a network function that does nothing except swap packets' MAC addresses.
Thus, it was optimized to do that as fast as possible, which made real-world code's performance worse.
While using a real-world workload would bring all kinds of questions about which workload, at least it would be better than measuring a completely unrealistic one.
