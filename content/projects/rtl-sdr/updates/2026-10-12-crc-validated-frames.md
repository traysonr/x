---
title: "A checksum turned a pulse pattern into real frames"
date: 2026-10-12
---

I went back to the original, unfiltered 60-second capture centered at 433.900 MHz. Two signals sat near 433.8885 and 433.9114 MHz. The first promising decode was mis-sliced; I had to stop trusting the bit string and look for structure that repeated.

The revised parser found a `D3 91` sync word, read the following length field, and checked a CRC-16 before accepting a frame. It recovered **396 CRC-valid frames** and rejected **67** apparent syncs that failed the check. The frames fall into two recurring groups: 84 short frames with payload `00`, and 312 frames with payload `11 22 33`. Both include the same sync and valid length/check fields.

![Counts and observed frame durations from the CRC-validated capture](packet-framing.svg)

That’s strong evidence for the framing, not an identity card for the transmitter. The header fields are still unknown, and `11 22 33` looks like a test pattern—but that last part is only a guess. Next useful experiment: capture while deliberately changing or powering the suspected device, then see which bytes move.
