Axis twist compensation may help if you are experiencing issues with inconsistency in your first layer. Please head the official Klipper documentation for more details. https://www.klipper3d.org/Axis_Twist_Compensation.html

Proceed at your own risk, however, the risk is minimal.

Instructions for implementation:
1. Copy axis_twist_compensation.py to /usr/share/klipper/klippy/extras/
2. Backup /usr/share/klipper/klippy/extras/probe.py
3. Delete /usr/share/klipper/klippy/extras/probe.py and probe.pyc
4. Copy my copy of probe.py to /usr/share/klipper/klippy/extras/
5. Add the following to printer.cfg  
    [axis_twist_compensation]  
    speed: 50  
    horizontal_move_z: 5  
    calibrate_start_x: 0  
    calibrate_end_x: 350  
    calibrate_y: 175  
    calibrate_start_y: 0  
    calibrate_end_y: 350  
    calibrate_x: 175  
7. Power Cycle the machine

In Fluide Console run  
AXIS_TWIST_COMPENSATION_CALIBRATE  

A new window will come up for you to adjust the z offset using the paper method (putting a piece of paper under the nozzle and lowering the Z until they touch). If oyu have feeler gauges, go with that. The goal here is to get the same resistance on all 5 probe points. I have always gone for the paper can be pulled out without tearing, or excess force, but cannot be pushed back in any further.

Do this for all 5 points.

In Fluide Console run  
AXIS_TWIST_COMPENSATION_CALIBRATE AXIS=Y

Do the same for all 5 points.

SAVE_CONFIG

Run a first layer test and see if it improves.
