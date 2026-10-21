---
title: "First question: how much of the radio should I build myself?"
date: 2026-09-27T12:39:17-07:00
---

The idea was to get a PIC and a Raspberry Pi talking over a pair of inexpensive FS1000A 433 MHz modules. I wanted to learn the whole path, but didn’t want to invent a protocol just for the sake of it. The useful split was to borrow the familiar pieces—preamble, sync, balanced coding, length, checksum—and define a small shared contract both ends could implement.

The first proof is intentionally one way: make the PIC send a known DATA packet and have the Pi receive and validate it. If that behaves, add acknowledgements and retries. Keeping the first milestone narrow gives us a clean place to debug before adding a round trip.
