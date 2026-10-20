---
title: "Faster sweeps, better questions for each hit"
date: 2026-10-17
---

The serial scan was doing a lot of retuning just to ask whether anything was there. Broad/Fast now groups the 2,652 configured channel centers into 97 wide windows, checks each for about 0.128 seconds, and extracts up to the three strongest channels when a window crosses threshold. On paper that’s about 12.4 seconds of probe time for a pass, before USB/FFT work, tuner settling, and the five-second triggered dwells.

It makes the survey much quicker, with a tradeoff: a brief burst can fall between probes, and only the strongest few channels in a busy window make it to full capture. This is a way to find leads, not continuous coverage.

I also pulled review into the scan screens: sort and filter candidates, play original or enhanced audio, mark a human voice label, add a frequency note, or send a candidate to Digital Scan. Audio enhancement only affects in-memory playback; it leaves the original WAV alone. A recent seven-pass review had 19 candidates. Several repeated narrow peaks near 444.9 MHz looked like receiver spill/spurs, so I grouped them for review rather than calling them transmissions.

The satisfying part is that the tool is becoming more honest about uncertainty. A candidate table is a queue for the next experiment, not a list of solved signals.
