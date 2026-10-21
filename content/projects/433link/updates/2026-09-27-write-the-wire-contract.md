---
title: "Write the packet contract before either side drifts"
date: 2026-09-27T15:28:09-07:00
---

I set up one repository for both processors: a shared protocol document at the root, a Raspberry Pi implementation, and a PIC handoff area. That gives the two sides one place to agree on bytes and timing while leaving timer and GPIO details with the firmware they belong to.

Protocol v1 uses ASK/OOK at a nominal 2,000 bits per second. Each logical bit becomes a Manchester pair (`0 → 01`, `1 → 10`), preceded by eight `0x55` bytes and sync `D3 91`. The packet carries version, type, source, destination, sequence, payload length, up to 32 payload bytes, then CRC-16-CCITT. That is enough structure to reject noise and malformed frames without making the first firmware pass huge.

![433Link v1 frame layout and reference test packet](frame-v1.svg)

The known DATA vector is `01 01 01 02 00 03 11 22 33 98 0E`: PIC address `01`, Pi address `02`, payload `11 22 33`, and CRC bytes `98 0E`. The CRC and byte order are spelled out in the protocol file so neither implementation has to guess.
