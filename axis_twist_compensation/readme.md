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
8. Home all Axes
9. In Fluidd console, run Z_TILT_ADJUST
10. Home Z
11. In Fluidd Console run AXIS_TWIST_COMPENSATION_CALIBRATE SAMPLE_COUNT=5  

    A new window will come up for you to adjust the z offset using the paper method (putting a piece of paper under the nozzle and lowering the Z until they touch). If oyu have feeler gauges, go with that. The goal here is to get the same resistance on all 5 probe points. I have always gone for the paper can be pulled out without tearing, or excess force, but cannot be pushed back in any further.

    Do this for all 5 points.

13. In Fluidd Console run AXIS_TWIST_COMPENSATION_CALIBRATE AXIS=Y SAMPLE_COUNT=5

    Do the same paper test for all 5 points.

14. In Fluidd Console run SAVE_CONFIG
15. Run a first layer test and see if it improves.
