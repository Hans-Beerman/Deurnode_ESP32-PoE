**KiCaD (concept) design Deurnode nieuw**

Current version: V0.4

This repository contains the KiCad design for Deurnode nieuw, a deurnode for the Makerspace Leiden. This new design is based on the use of an Olimex ESP32-PoE.

**This Deurnode Nieuw has the following features:**

- Two digital inputs are available. By means of a jumper the following options are available:

Option 1:

-
  - 1x Simple digital switch input (to be used for the Grote Schakelaar e.g.)
  - 1x Opto coupler input

Option 2:

-
  - 2x opto coupler input

Both opto couplers can be used to detect 230V AC available or not. By changing the input resistors of the optocouplers the inputs can be used for other voltages as well

- 1 digital output is available. By means of two jumpers the following options are available:
  - Digital output, to directly control a buzzer
  - Digital output to switch a coil or so. There are two options:
    - A relais controlled output (max. 250V AC/10A)
    - A FET based output based on Polu Breakout A4988.

The FET can handle max DC 55V/35 A. In that case the FET most likely must be kept cool by means of a small cool block.

- SPI based RFID reader connection
- Step motor output

**Power supply:**

Depending on how the deurnode is used, there are two options to provide power to the deurnode print:

1. The ethernet port of the Olimex ESP32-PoE board is directly connected to the MSL LAN. J19 must be removed in this situation. In that case there is no 12V available. It is however possible to provide 12V with an external PSU. Without external 12 V the step motor and the buzzer will not function at all and also the 12V output for the FET will not be available.
2. To power the board via an external PSU (only). J19 must be installed and the ethernet board of the Olimex board should not be connected to a PoE cable.

The following solution is available to couple the deurnode directly to a PoE connection of MSL LAN and also provide 12V to the deurnode board. See the diagram in the file &quot;Deurnode Nieuw power supply V0.1 20200302.pdf&quot;

For this solution a PoE splitter is used. On the Deurnode board jumper J19 must be installed.

**Protection 230V circuits for the opto couplers**

To prevent hazardous shocks, plexiglass plates can be mounted on the board. The board contains 6 holes to mount these plates.

For more information over these protection plates, see the &quot;DeurnodeProtection-230V.pdf&quot; or the Autocad &quot;DeurnodeProtection-230V.dwg&quot; files.