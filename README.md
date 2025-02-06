This repository contains custom configuration files for OrcaSlicer, tuned for performance with an emphasis on speed. These profiles are designed for an Ender 3 equipped with a BTT SKR Mini E3 V3, Creality Sprite Pro hotend, CR Touch auto-leveling sensor, a PEI bed, and dual Z axes.

Hardware Overview
Printer: Ender 3 with dual Z
Controller: BTT SKR Mini E3 V3 running Klipper firmware
Hotend: Creality Sprite Pro (hardened steel nozzle)
Auto Bed Leveling: CR Touch
Build Surface: PEI
Firmware: Klipper
Repository Structure
./hints.cereal
Optional hints file (currently empty) for additional printer hints if needed.

./.gitignore
Ignores files like .DS_Store to keep the repository clean.

./default/filament/
Contains filament profiles (e.g., Bender PLA.json and its info file) with temperature, flow, and cooling settings.

./default/machine/
Contains machine configurations (e.g., Ender 3 – Klipper.json and its info file) that define motion parameters, start/end G-code, and physical limits.

./default/process/
Contains slicing process profiles tuned for speed and performance (e.g., 0.20mm Standard @Bender.json and common FDM process settings).

Performance Tuning Philosophy
These configurations have been tuned to reduce print times without compromising the essential quality and reliability of prints. Key adjustments include:

Higher Accelerations & Jerk Values:
Aggressive settings (e.g., default acceleration increased to 8000 mm/s² and above) reduce idle time during printing. Monitor for ringing or mechanical stress and adjust if necessary.

Increased Speeds:
Enhanced travel, extruding, and support speeds (e.g., travel speeds up to 400 mm/s) help shorten non-print moves. Be mindful of potential artifacts at extreme speeds.

Optimized Retraction & Bridge Settings:
Adjusted retraction lengths and speeds improve transition times and reduce stringing, while bridge acceleration and speed values are raised to cut bridging times—test for overhang quality.

First-Layer Conservatism:
First-layer speeds and accelerations remain moderated to ensure bed adhesion and a solid print foundation.

Usage Instructions
Klipper Integration:
Import the machine configuration (Ender 3 – Klipper.json) into your Klipper setup. Ensure that your firmware settings are aligned with these values and that your hardware can handle the increased motion parameters.

OrcaSlicer Setup:
Load the filament and process profiles into OrcaSlicer. Verify that the profile names and paths match those referenced in the slicer settings.

Incremental Tuning:
Use the included diff suggestions as a baseline for performance tuning. It’s recommended to apply changes gradually and test with calibration prints. Adjust acceleration, jerk, and speed settings if you notice artifacts or mechanical issues.

References
Klipper Configuration Reference
OrcaSlicer GitHub Repository
