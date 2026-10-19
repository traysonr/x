---
title: "Linkage layout and workspace"
date: 2026-03-18T14:00:00-07:00
---
I settled on a shoulder, elbow, and wrist arrangement with a fixed base rotation. The first CAD pass prioritizes accessible fasteners and keeping the arm light enough for hobby servos.

## Control sketch

The initial controller maps target points in the arm plane to two joint angles. I?m keeping the kinematics in a small module so it can be tested independently from the servo driver.

```python
def solve_planar(x, y, upper, forearm):
    # Return shoulder and elbow angles for a reachable point.
    cos_elbow = (x*x + y*y - upper*upper - forearm*forearm) / (2*upper*forearm)
    elbow = math.acos(max(-1.0, min(1.0, cos_elbow)))
    shoulder = math.atan2(y, x) - math.atan2(forearm*math.sin(elbow), upper + forearm*math.cos(elbow))
    return shoulder, elbow
```
