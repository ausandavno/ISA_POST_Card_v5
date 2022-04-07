# ISA_POST_Card_v5.1
Version 5.1 of a plug-in diagnostic card that displays Power On Self Test (POST) codes on an 8-bit ISA data bus. Tested for use with Micro8088 and Xi8088 systems. Can be configured to listen on any address in the lower ten bits of address space. 

## Hardware Documentation

### Schematic and PCB Layout

[Schematics - Version 5.1 (pdf)](Schematics/ISA_POST_Card_v5.1-Schematic.pdf)

[PCB Layout - Version 5.1 (zip)](Gerbers/ISA_POST_Card_v5.1-PCB_Layout.zip)

### Building Instructions

Recommend soldering components in order of height, lowest to highest: Resistors (Rx), IC sockets (if used), Resistor Networks (RNx), Capacitors (Cx), Discrete LEDs (Dx), Seven Segment LEDs (LEDx), Switches (SWx).

Recommend populating turned-pin strip headers for U2, U3, U9 and U10. Populate U2, U3 if intending to use seven-segment display driver 74LS47. Populate U9, U10 if intending to use ATF16V8B-15PU to display hexadecimal values.

### Jumpers, Connectors, and Switches

#### JP1 - Select chip options for U1
Position | Description
-------- | -----------
1-2 closed (default)* | Use 74x273 Series
2-3 closed | Use 74x374 Series

*Cut trace to open 1-2

#### SW1 - Lowest five bits of address space selection
Position	| Description
-------- | -----------
SW1.1 | bit 4 of address space
SW1.2 | bit 3 of address space
SW1.3 | bit 2 of address space
SW1.4 | bit 1 of address space
SW1.5 | bit 0 of address space (LSB)

#### SW2 - Highest five bits of address space selection
Position	| Description
-------- | -----------
SW2.1 | bit 9 of address space (MSB)
SW2.2 | bit 8 of address space
SW2.3 | bit 7 of address space
SW2.4 | bit 6 of address space
SW2.5 | bit 5 of address space

### Bill of Materials - v5.1

Component type     | Reference | Description            | Quantity | Possible sources and notes 
------------------ | --------- | ---------------------- | -------- | --------------------------
PCB                |           | ISA Post Card v5.1     | 1        | Use supplied Gerber or KiCad files to order from your perferred PCB fabrication house
Integrated Circuit | U1        | 74ALS273 or 74ALS374 (See JP1 Setting)   | 1        | Mouser [SN74ALS273N](https://www.mouser.com/ProductDetail/595-SN74ALS273N) or [SN74ALS374AN](https://www.mouser.com/ProductDetail/595-SN74ALS374AN)
Integrated Circuit | U2, U3    | 74LS47 (Alternative to U9, U10)   | 2        | Mouser [SN74LS47NE4](https://www.mouser.com/ProductDetail/595-SN74LS47NE4)
Integrated Circuit | U4, U5    | 74ALS521 or 74HCT688   | 2        | Mouser [SN74ALS521N](https://www.mouser.com/ProductDetail/595-SN74ALS521N) or [CD74HCT688E](https://www.mouser.com/ProductDetail/595-CD74HCT688E)
Integrated Circuit | U6, U7    | 74HC132                | 2        | Mouser [CD74HC132E](https://www.mouser.com/ProductDetail/595-CD74HC132E)
Integrated Circuit | U8        | 74LS74                 | 1        | Mouser [SN74LS74AN](https://www.mouser.com/ProductDetail/595-SN74LS74AN)
Integrated Circuit | U9, U10   | ATF16V8B (Alternative to U2, U3) | 2        | Mouser [ATF16V8B-15PU](https://www.mouser.com/ProductDetail/556-AF16V8B15PU)
LED    | LED1, LED2   | 7-Segment Display W7.4mm H10mm  | 2        | Mouser [LTS-2801AG](https://www.mouser.com/ProductDetail/859-LTS-2801AG) or [LTS-2801AWC](https://www.mouser.com/ProductDetail/859-LTS-2801AWC)
LED | D1 - D4   | LED_D3.0mm    | 4        | Mouser [LTL-4231N](https://www.mouser.com/ProductDetail/859-LTL-4231N)
Resistor Network   | RN1, RN2  | R_Array_SIP6 10K (Bussed)      | 2        | Mouser [4606M-101-103LF](https://www.mouser.com/ProductDetail/652-4606M-1LF-10K)
Resistor Network   | RN3 - RN6  | R_Array_SIP8 1K (Isolated)   | 4    Mouser [L083S122LF](https://www.mouser.com/ProductDetail/858-L083S122LF)
Resistor   | R1  | R_Axial_DIN0207 L6.3mm D2.5mm P10.16mm 10K       | 1        | Mouser [MFR-25FRF52-10K](https://www.mouser.com/ProductDetail/603-MFR-25FRF5210K)
Resistor   | R9, R13  | R_Axial_DIN0207 L6.3mm D2.5mm P10.16mm 1k | 2 | Mouser [MFR-25FRF52-1K](https://www.mouser.com/ProductDetail/MFR-25FRF52-1K)
Resistor   | R10, R14  | R_Axial_DIN0207 L6.3mm D2.5mm P10.16mm 2.4k | 2 | Mouser [MFR-25FRF52-2K4](https://www.mouser.com/ProductDetail/603-MFR-25FRF52-2K4)
Capacitor   | C1 - C8  | P5.08mm 0.1uF     | 8        | Mouser [FG28X7R1H104KNT06](https://www.mouser.com/ProductDetail/810-FG28X7R1H104KNT6)
Capacitor   | C9  | P5.08mm 10uF     | 1        | Mouser [FG24X7R1A106KRT06](https://www.mouser.com/ProductDetail/810-FG24X7R1A106KRT6)
Switch   | SW1, SW2  | SW_DIP_SPSTx05_Slide 9.78x14.88mm W7.62mm P2.54mm   | 2    | Mouser [CTS 206-5](https://www.mouser.com/ProductDetail/774-2065) or [C&K BD05](https://www.mouser.com/ProductDetail/611-BD05)


### Alternative ICs



## Firmware Documentation

### ATF16V8B

## Changes
* Version 5.1
  * First Issue

## Known Issues
* Version 5.1
  * None at present
