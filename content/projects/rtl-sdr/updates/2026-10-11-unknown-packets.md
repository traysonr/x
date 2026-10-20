---
title: "Known weather packets, then an unknown one"
date: 2026-10-11
---

At 433.94 MHz, `rtl_433` gave me a nice sanity check: it recognized repeating Oregon weather-sensor packets and produced structured readings. That confirmed the capture-and-decode path was working for at least one known format.

Then a targeted capture around 433.9125 MHz produced a pulse train that the built-in decoders didn’t recognize. I generated a local report with the pulse timing and signal plots, and started treating it as an unknown packet format instead of calling it a device. My first bit slicing was wrong; what looked like a short frame was a parsing artifact. Keeping the capture made it possible to revisit the same RF data as the parser improved.

![Radio Automation Console set up for a targeted 433.900 MHz digital capture](console-digital.jpg)

The digital workflow now records raw I/Q and keeps the decoder’s report with the run. A pulse viewer is a useful clue, but it is not a protocol identification by itself.
