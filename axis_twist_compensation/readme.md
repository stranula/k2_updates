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
    calibrate_start_x: 20
    calibrate_end_x: 330
    calibrate_y: 175
    calibrate_start_y: 20
    calibrate_end_y: 330
    calibrate_x: 175
6. Power Cycle the machine