---
title: "433Link: a PIC-to-Pi radio link"
description: "A small custom packet link between a Raspberry Pi 3 and a dsPIC33CK64MC105, using inexpensive 433 MHz ASK/OOK modules. The first milestone is deliberately one way: get a known PIC packet into the Pi, validate it, then work toward ACKs and retries."
date: 2026-09-27
tags: ["Embedded systems", "Raspberry Pi", "dsPIC33", "Python", "433 MHz RF"]
thumbnail: "hero.svg"
hero: "hero.svg"
---

I wanted a radio project where I could follow the whole path: bytes in firmware, a signal over the air, and a decoded packet on a Raspberry Pi. The FS1000A modules are cheap and a little rough around the edges, which makes them a good excuse to learn the framing and timing instead of treating the radio as a black box.

The first target is a known DATA packet from the PIC to the Pi. Once that works reliably, the plan is to add acknowledgements and retries. So far the useful progress is the shared protocol contract and a tested, hardware-independent Pi implementation. **The repository does not yet show a verified over-the-air packet; the GPIO receiver and PIC firmware still need to meet at the bench.**

The [433Link repository](https://github.com/traysonr/433Link) has the protocol contract, Pi reference code, and PIC handoff notes.
