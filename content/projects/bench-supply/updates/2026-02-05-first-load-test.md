---
title: "First electronic load test"
date: 2026-02-05T10:15:00-07:00
---
The first pass uses a commercial buck module, a shunt amplifier, and a microcontroller for display and control. I tested into a resistive load at 5 V and 12 V while logging output ripple.

![Ripple measurement](../ripple.svg)

Ripple rises with load, so the next iteration will shorten the output wiring and add local capacitance at the binding posts. The current limit trips consistently, but its calibration needs a more precise reference.
