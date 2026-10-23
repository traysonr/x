---
title: "From one-off scripts to a review console"
date: 2026-10-12
---

Once the overnight scan started producing hundreds of candidates, I needed a place to review them without losing the trail. I built a small PySide desktop app with separate Basic Scan, Broad/Fast Scan, and Digital Scan modes, dated run folders, profiles, capture playback, and a shared encounter log.

The first classifier pass was deliberately a screen, not a verdict. Replaying the 2026-10-11 run with version 2.0 left **533 noise**, **198 review**, and **1 voice** candidate. I kept the review bucket wide because weak audio and unknown modulation are easy to mislabel. A person can mark voice/no voice after listening; those labels are saved for future analysis, but they do not train the current classifier.

That distinction matters: the app can help sort a pile of captures, but only listening or a decoder can confirm what a particular hit was. The later storage cleanup also made clear that raw I/Q is valuable and expensive. Capture retention needs to be a conscious choice, not an accidental side effect of an overnight run.
