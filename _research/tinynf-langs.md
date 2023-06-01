---
title: Safe Low-Level Code Without Overhead is Practical
excerpt: Decoupling low-level safety from correctness is the way to go
date: 2023-05-19
venue: ICSE '23
authors: S. Pirelli, G. Candea
artifact: https://github.com/dslab-epfl/tinynf
video: https://youtu.be/zMm7rODMjws
---

Since I had a small, self-contained, and fast driver for Intel's 82599 NIC through the [TinyNF](/research/tinynf) project,
I decided to see if translating that driver to other languages would yield interesting results.
This wouldn't have been realistically feasible with typical drivers that are large and have a lot of dependencies on other libraries.
It was the first time I wrote code in Ada, which is a fun but somewhat frustrating experience I would recommend to anyone interested in programming languages.


## Problem

High-level languages such as C# and Rust require compilers to insert safety checks, such as bounds checks when indexing arrays.
This is good for most code that doesn't have strict performance requirements, but causes some overhead.
As long as that overhead is non-zero, some developers will continue using unsafe languages such as C in the name of performance, causing all the problems that come with unsafety.


## Hypothesis

Simple type invariants such as "non-null pointer" and "integer in a specific range" are enough for trivial safety proofs within a compiler.
That is, the compiler does not need extra information such as proof annotations, does not need to use heuristics, and does not need to call a solver to prove low-level safety.
Safety here refers to crash-freedom and memory safety, not higher-level concepts such as noninterference between tenants.


## Results

Our drivers in C# and Rust, which use language extensions we designed to add more type invariants, are as fast as the existing C baseline.
Our driver in Ada, which does not need any extensions, is also as fast as the C baseline.
None of the drivers have any run-time checks at all.


## Limitations

Because current compilers for high-level languages were not designed for zero-overhead safety, they do not provide enough information
to understand why they insert run-time checks, making the process of writing a safe driver without run-time overheads rather frustrating.
One must guess a code shape that feels right, compile the code, check the assembly, and try again if there are any inserted checks.
Even in Ada which has the necessary type invariants built in, the GNAT compiler sometimes inserts unexpected checks.


## Lessons Learned

**Artifacts are reusable.** This work wouldn't have happened if I hadn't prepared a proper artifact with benchmarking script as part of
the original TinyNF work. Whatever effort went into that paid for itself multiple times over.

**Question folk wisdom.** This is not revolutionary advice, but it's really the core of this paper: forget about everyone who believes
safety requires performance sacrifices, can we show it doesn't for some interesting use case?
I'm looking forward to potential future papers telling me I'm wrong because in XYZ domain it's not possible. At least now the burden of proof is on whoever wants to claim that.
