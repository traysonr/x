---
title: "The wiring question was part of the protocol work"
date: 2026-09-30T17:32:34-07:00
---

When the modules came out on the bench, the receiver’s `5V` marking raised the important question: what voltage is actually coming back out of `DATA`? The Pi’s GPIO is 3.3 V. Feeding the module from 5 V does **not** make a 5 V DATA output safe for a Pi pin.

The sensible next step is to measure the receiver output and use a level shifter or divider if it exceeds the Pi’s input limit. The conversation stopped before that was verified, and I don’t see a captured packet or concrete GPIO receiver in this repo. So the honest status is: protocol and offline software are in place; the first over-the-air receive is still ahead.

![The intended PIC-to-Pi path for the first milestone, shown as a design diagram rather than a measured link](hero.svg)
