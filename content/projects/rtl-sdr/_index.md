---
title: "RTL-SDR radio automation"
description: "A Python based radio survey and packet analysis workbench for an RTL-SDR: scanning VHF/UHF channels, triaging captures, and figuring out what unknown signals are actually saying."
date: 2026-10-04
tags: ["Python", "RTL-SDR", "Signal processing", "RF"]
thumbnail: "console-basic.jpg"
hero: "console-digital.jpg"
---

This started as a weekend idea: let a cheap USB radio sweep channels, save anything interesting, and help me sort the hits afterward. It has grown into a small desktop workbench for scanning, replaying captures, and poking at signals that don’t come with a decoder.

The receiver is an RTL-SDR. Python handles the scan and review workflow; `rtl_433` helps identify supported devices, and small analysis scripts fill in the gaps when it doesn’t. A hit is a lead, not an identification: scan dwell time, antenna, local interference, and the receiver setup all affect what makes it into the log.
