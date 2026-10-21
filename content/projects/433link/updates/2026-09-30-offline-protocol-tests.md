---
title: "Make the packet work in software before blaming the air"
date: 2026-09-30T17:48:33-07:00
---

The Pi side now has a small, testable path for building and checking packets: a packet model, CRC, Manchester codec, and a frame parser that searches for preamble/sync before validating length and checksum. The conversation’s Pi session reported **63 pytest checks passing**. That’s encouraging for the software protocol path; it says nothing yet about receiver timing over the radio.

One useful design boundary is still visible in the code: GPIO timing is an interface, not a finished `pigpio` implementation. The current command-line tool decodes logical packet bytes offline. The PIC folder in this repository is still a handoff/readme, so I’m not counting firmware behavior as demonstrated here.
