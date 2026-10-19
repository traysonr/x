---
title: "First prototype and power budget"
date: 2026-04-12T09:30:00-07:00
---
The first bench prototype uses a small microcontroller board, a digital temperature and humidity sensor, and a light sensor. The immediate goal is to measure sleep current before choosing a battery and panel.

## Initial power estimate

| Mode | Current | Duration per hour |
| --- | ---: | ---: |
| Deep sleep | 22 ?A | 58 min |
| Sensor sample | 8 mA | 2 s |
| Radio upload | 42 mA | 3 s |

The radio dominates the short active window. Next I?ll verify the real average with a current profiler and check the sensor readings against a reference thermometer.

```c
// Simplified sampling loop
wake_sensor();
read_environment(&temperature_c, &relative_humidity);
store_sample(temperature_c, relative_humidity);
sleep_until_next_interval();
```
