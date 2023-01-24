---
title: Automated Verification of Network Function Binaries
excerpt: Source code isn't necessary to verify what developers have written
date: 2022-04-05
venue: NSDI '22
authors: S. Pirelli, A. Valentukonytė, K. Argyraki, G. Candea
artifact: https://github.com/dslab-epfl/klint
video: https://youtu.be/k3wlhQUr9VE
doi: https://www.usenix.org/conference/nsdi22/presentation/pirelli
---

A direct follow-up to [Vigor](https://doi.org/10.1145/3341301.3359647), and other work like [Gravel](https://www.usenix.org/conference/nsdi20/presentation/zhang-kaiyuan), that solves two key issues.
It retains the assumption that data structures are too complex for automated verification and are manually verified separately, though.


## Problem

Operators would love to deploy verified code, but developers may not want to reveal their source code nor use some operator-specific verification-friendly framework to write code.
Previous work made important steps in verification but requires source code and the use of specific data structures.
This limits the practical applicability of network function verification.


## Hypotheses

The typing information previous work used is actually redundant with the information already in function declarations for dynamically linked code.
Furthermore, the detailed information provided by contracts for data structures is not necessary as they could be abstracted away through a single data structure.


## Results

It is possible to automatically verify the parts of network functions developers write, i.e., not the data structures themselves nor the packet-processing framework,
even using only binaries, and regardless of which data structures they use.
In fact, abstracting data structures through maps makes the tool considerably simpler, and enables better invariant inference since the tool can specialize for maps.
Furthermore, it is possible to implement map operations in a way that does not use data structures in SMT, thus making verification decidable.


## Limitations

Some niche data structures cannot reasonably be abstracted away as maps. Unfortunately, this includes regular expressions for applications like packet inspections.

The technique is also not applicable for general-purpose software as it requires detailed modelling of the packet-processing framework,
which is possible because their API surface is generally narrow and rather shallow. For instance, no matter what packets are transmitted, any packet could be received.
This would not apply to, say, a kernel, because the models would have to faithfully emulate behaviors such as what happens when a file is opened or closed.


## Lessons Learned

**Less is more.** The tool is actually simpler, both conceptually and in its implementation, than previous tools that used source code and special-cased some data structures.
Instead of starting from whatever you happen to have, question what the bare minimum is for your goal, do that, then think about why extra information might be useful.
Ideally, the tool could use debug symbols if they are available to improve the debuggability of verification failures, but we didn't try to implement this.

**Build on the shoulder of giants.** The tool is based on [angr](https://angr.io), an open source symbolic execution engine for binaries.
This work would have taken forever if we'd had to manually model even the somewhat common x86 instructions, but we didn't have to.
And we [contributed back](https://github.com/angr/claripy/pull/242), too!

_Fun fact: while working on this, I one day decided to run verification on one of the lab's servers instead of my laptop, so I could run experiments overnight easily.
Next time I benchmarked the tool, it was 4x slower, so I spent a few days optimizing low-hanging fruit. Then I realized the server I had logged into was our oldest one,
whose single-core performance is 1/4th that of my laptop... so there was no regression in the first place. Thankfully this wasn't close to the deadline, so I did not waste too much time..._
