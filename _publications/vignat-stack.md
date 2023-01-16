---
title: A Formally Verified NAT Stack
excerpt: Extending automated verification to a library and a driver
date: 2018-08-20
venue: SIGCOMM KBNets Workshop '18
authors: S. Pirelli, A. Zaostrovnykh, G. Candea
artifact: https://github.com/vignat/vignat/tree/kbnets18
video: https://youtu.be/esfwD46f2ZI
doi: https://doi.org/10.1145/3310165.3310176
remarks: Best Paper Award
---

My first paper as first author!
This paper was my Masters thesis, extending [previous work](https://doi.org/10.1145/3098822.3098833) from the lab on formally verifying a Network Address Translator.
It was a stepping stone toward the ["Vigor" paper](https://doi.org/10.1145/3341301.3359647) published at SOSP'19.

As it got the KBNets workshop's Best Paper Award, it was [republished in SIGCOMM CCR](https://doi.org/10.1145/3310165.3310176).


## Problem

Most of the code in a user-space network function is not code that its authors wrote but library code, thus verifying only the code authors wrote is not enough.
If any of the libraries, such as the network card drivers, have a bug, then the network function has a bug, even if the code its authors wrote is bug-free.


## Hypothesis

Most library code is not actually executed, and the code that is executed is straightforward, consisting of a small number of "success" paths and a bunch of "error" paths that exit early.
Thus, we should be able to symbolically execute library code to verify its low-level correctness properties automatically, and even verify some high-level correctness properties
using models of the environment such as the network card.


## Results

It is indeed possible to use symbolic execution, at least for the DPDK user-space networking library and its driver for the Intel 82599 NIC.
We verify that, in the context of the "VigNAT" Network Address Translator, they correctly interact with the Linux kernel and the network card hardware.
This represents over an order of magnitude more source code, though most of it is unused by VigNAT.

We found [bugs](https://bugs.dpdk.org/buglist.cgi?component=core&component=ethdev&email1=Pirelli&emailreporter1=1&emailtype1=substring&product=DPDK)
while doing this verification: a few edge cases in DPDK, such as "DPDK will crash at startup on a machine with >128 cores if the first 128 ones are disabled",
and some bugs in how the NIC driver communicated with the NIC... at least bugs according to the data sheet. The driver authors did not always agree, since the code worked in practice.


## Limitations

We model the C standard library and the Linux kernel, thus bugs may still hide in there.

Our models for libC, Linux, and the NIC are based on human-readable data sheets, as we did not find machine-readable specifications to use.
Thus, it's possible that the models do not match reality, for instance due to ambiguities in the text.
This is particularly true for the NIC, whose data sheet is long and not a linear read.


## Lessons Learned

**Targeting a workshop for an undergrad thesis is a great idea!**
It's unlikely undergrad work can lead to a full publication, but there's probably a workshop colocated with a good venue that would be interested.
This gave me a clearer idea of what a PhD would be like, including preparing a paper.
The page limit also ensures time is spent wisely instead of spending ages writing endless pages on all possible related work.

**When verifying, start by modelling _all_ of the environment.**
I started by modelling the network card only. It was quite a pain to get DPDK to call the real libC in just the right way, and that effort was wasted in retrospect.
Instead, I should have started by delimiting what was in scope for verification and what was not, and modelling everything not in scope. The scope can always change later,
and the models may not be exhaustive at first, but having control over the entire environment at all times drastically improves productivity.
