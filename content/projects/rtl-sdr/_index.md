---
title: "RTL-SDR signal scanning and analysis"
description: "Python RF scanning and triage, from thousands of VHF/UHF channel checks to CRC-validated packet captures."
date: 2026-10-04
tags: ["Python", "RTL-SDR", "Signal processing", "RF"]
thumbnail: "signal-spectrum.png"
hero: "signal-spectrum.png"
heroCaption: "A derived 10-second channelized I/Q slice from the 433.900 MHz capture. The lower panel shows the normalized spectrum; the upper panel shows packet activity over time."
---

This started as a weekend idea: let a cheap USB radio sweep channels, save anything interesting, and help me sort the hits afterward. It has grown into a Python workbench for scanning, replaying captures, and investigating signals that don’t come with a decoder.

The receiver is an RTL-SDR. Python handles the scan and review workflow; `rtl_433` helps identify supported devices, and small analysis scripts fill in the gaps when it doesn’t. A hit is a lead, not an identification: scan dwell time, antenna, local interference, and the receiver setup all affect what makes it into the log.
