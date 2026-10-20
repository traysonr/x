---
title: "Keep the I/Q; audio can wait"
date: 2026-10-10
---

Saving only demodulated audio was a dead end for digital signals. I switched the hit recorder to keep raw complex samples alongside the NFM WAV, so I could come back later and try another filter or decoder without needing the radio to hear the transmission again.

That exposed a couple of practical wrinkles. The scan notices a signal before it starts the five-second capture, so a short transmission can be mostly gone by then. And for NFM, filtering the channel before FM demodulation made a much cleaner result than trying to demodulate the whole 1.024 MHz capture first. A nearby DMR repeater also explained why a strong hit could sound like hash on the analog audio path: strong RF isn’t the same thing as analog voice.

Keeping every full-rate capture quickly became a storage problem—one overnight run produced about 6.35 GB. That pushed storage and review into the design instead of treating captures as disposable debug files. I started narrowing the scan profile and keeping the raw recording where it could answer a real question.
