# dual-host-sd
Dual host SD card PCB designed to be controlled by RP2040 MCU over ethernet to accurately control 3D printer automation. This specific version is used in a 3D printing farm consisting of Bambu A1 Minis.

<img src="PCB%20Layout.png" alt="PCB Layout" width="400">


## Hardware
- RP2040-ETH (or any MCU with ethernet capabilities)
- 5V Blower Fan (for cooling of 3D printer bed)
- 1-channel 3.3 V opto-isolated relay module, rated up to 10 A at 250 VAC (to turn off the 3D printer when SD card is written to)
- SD card
- If assembling the PCB yourself, refer to the BOM for the complete parts list

## Software 
- C/C++
- Raspberry Pi Pico SDK

## Notes
- The PCB must be ordered as a flex PCB with a finished thickness of 0.1 mm. The stiffener near the SD-card contact pads must be 0.8 mm. Confirm the stiffener requirements with the PCB manufacturer before ordering. This PCB will work natively with JLCPCB.
- 3D printer is turned off using relay so that the SD card can get written to, and the 3D printer can power cycle which is important in an automated farm.
- Only one SD card host is connected at a time. Ensure RP2040-ETH disconnects its lines via the MUX before the 3D printer is turned on.

