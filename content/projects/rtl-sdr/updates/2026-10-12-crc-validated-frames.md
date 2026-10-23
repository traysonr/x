---
title: "A checksum turns pulse patterns into frames"
date: 2026-10-12
---

I went back to the original, unfiltered 60-second capture centered at 433.900 MHz. Two signals sat near 433.8885 and 433.9114 MHz. The first promising decode was mis-sliced; I had to stop trusting the bit string and look for structure that repeated.

The revised parser found a `D3 91` sync word, read the following length field, and checked a CRC-16 before accepting a frame. From this 60-second capture it recovered:

- **396 CRC-valid frames**
- **67** apparent syncs rejected by the CRC
- **84** group A frames with payload `00`
- **312** group B frames with payload `11 22 33`

{{< figure src="packet-framing.svg" alt="Counts and observed frame durations from the CRC-validated capture" caption="Observed frame groups and durations from the retained capture. These are parser results, not device identifications." >}}

{{< bit-viewer >}} to inspect the two recovered packet types byte by byte.

That’s strong evidence for the framing, not an identity card for the transmitter. The header fields are still unknown, and `11 22 33` looks like a test pattern—but that last part is only a guess. Next useful experiment: capture while deliberately changing or powering the suspected device, then see which bytes move.
