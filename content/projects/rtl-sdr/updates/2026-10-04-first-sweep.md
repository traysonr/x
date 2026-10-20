---
title: "First sweep: make the radio do the boring part"
date: 2026-10-04
---

The first version was a Python loop around the RTL-SDR: tune a channel, take a short look, and save a capture when the signal crossed a threshold. The goal was simple—cover the local VHF/UHF channels without sitting there retuning by hand.

The first broad grid had 5,601 channels. At a quarter second per probe, one pass could take roughly 23 minutes before tuner settling or file work. That was too slow for casual experiments, so I added focused profiles for the bands and frequencies I actually wanted to watch. A plotted sweep also made one strong, repeatable feature around 445.0375 MHz stand out. That was a useful lead, but a peak alone doesn’t tell me what modulation or user is behind it.

I also ran into a driver/API mismatch while setting frequency correction. Fixing the startup path got the receiver running reliably; after that, the bigger question was what to save when a hit appeared.
