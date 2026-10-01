# dual-host-sd
Dual host SD card PCB designed to be controlled by RP2040 MCU over ethernet to accurately control 3D printer automation. This specific version is used in a 3D printing farm consisting of Bambu A1 Minis.

<img src="v2/PCB%20Layout.png" alt="PCB Layout" width="400">
<img src="v2/Flex%20SD%20PCB.png" alt="PCB Layout" width="400">

## Capabilities
- AC power to 3D printer (ability to monitor print farm power usage + power cycle printer for reliability)
- AC power is converted to DC for MCU and SD card side (fused for reliability)
- Blower fan for bed cooling
- Servo capabilities for enclosed printers
- SD card .gcode file transfer to printer
- LEDs for overhead CV planar positioning across the farm
- Manual buttons for human intervention

## Hardware
- RP2040-ETH
- 5V Blower Fan (for cooling of 3D printer bed)
- 1-channel 3.3 V opto-isolated relay module, rated up to 10 A at 250 VAC (to turn off the 3D printer when SD card is written to)
- 2× SD card (1x printer gcode; 1x RP2040 cache from ethernet to printer card)
- Servo

## Software 
- C/C++

## Notes
- v2 features a secondary PCB as a simple flex PCB to connect to the SD card
- Only one SD host connected at a time, RP2040-ETH must disconnect via the MUX before the printer powers on
- Confirm stiffener thickness with your manufacturer for the flex PCB
- North American 120 V mains path