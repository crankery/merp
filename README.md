# Merp

🛑 This is untested. Do not build this thing. I will post an update when it's been tested.

Modular Eurorack Powerbus (Merp) is yet another power bus [KiCad](https://www.kicad.org/) project. Yes, we're truly breaking new ground here... This has never been done before.

I think the only differentator with this from the other power bus PCBs is that this one is designed to be ordered from one of the Chinese PCB fabs for their minimum price. The width of the board is 100mm while the height is much less than that. [PCBWay](https://www.pcbway.com/) for example currently has 5 boards for $5 if they're under 100mm x 100mm. If you order 5 boards you can connect them all together and have 30 x 16 pin Doepfer sockets (I hope you have 104 hp rails if you're doing that). 

This board rquires +12V, -12V and +5V supplies. I'm using [Meanwell RT-65](https://www.meanwell.com/webapp/product/search.aspx?prod=RT-65) to power mine. The board has no +5V conversion and does no power regulation. If none of your Eurorack modules use +5V you can get away without it.

The mounting holes are suitable for M3 bolts & standoffs. Through hole components are used exclusively.  

# Renders

Here's some pictures of the board that KiCad generated.

## Front

![](images/merp_front.png?raw=true)

## Front Again

![](images/merp_front2.png?raw=true)

The red stripe on Eurorack module power connectors should be towards the bottom of the board as indicated.

## Back

![](images/merp_back.png?raw=true)

# Notes

- The resistor values are just a guess. They're simply there to make the power indicator LEDs a bit dimmer.
- The LEDs and the pin headers below them are the same thing. If you're connecting an LED via a header, ensure the positive leg connects to the + pin.
- If you don't want to use the LEDs you can leave the resistors, LEDs and associated headers unpopulated. They are not required for operation of the power bus.
- The interconnect header & socket are shown to be mounted on the back on the boards. The boards are intended to be installed in your Eurorack case on standoffs.
- If you don't want to connect a module to the left or right, leave the interconnect header or socket unpopulated.
- There's an additional power header on the left side of the board. This header is entirely optional.
- You can probably only populate the filter capacitors on one of your boards. Or none of them... They're optional.
- All signals are passed through all interconnected power bus modules.
- The Gate and CV lines of the Doepfer bus are connected, inclusive of module interconnects.

# BOM

(Yeah, I know this needs work)

|Id |Designator |Package                                         |Quantity|Designation    |Supplier and ref|FIELD7|FIELD8|
|---|-----------|------------------------------------------------|--------|---------------|----------------|------|------|
|1  |R2,R3      |R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal|2       |47k            |                |      |      |
|2  |J2         |IDC-Header_2x08_P2.54mm_Vertical                |1       |B              |                |      |      |
|3  |C3,C2,C1   |CP_Radial_D8.0mm_P3.50mm                        |3       |47uF           |                |      |      |
|4  |J10        |PinHeader_1x02_P2.54mm_Vertical                 |1       |-12V           |                |      |      |
|5  |J1         |IDC-Header_2x08_P2.54mm_Vertical                |1       |A              |                |      |      |
|6  |J9         |PinHeader_1x02_P2.54mm_Vertical                 |1       |+12V           |                |      |      |
|7  |H3,H2,H1,H4|MountingHole_3.2mm_M3_DIN965_Pad                |4       |GND            |                |      |      |
|8  |J4         |IDC-Header_2x08_P2.54mm_Vertical                |1       |D              |                |      |      |
|9  |J3         |IDC-Header_2x08_P2.54mm_Vertical                |1       |C              |                |      |      |
|10 |D3         |LED_D3.0mm                                      |1       |-12V           |                |      |      |
|11 |D1         |LED_D3.0mm                                      |1       |+5V            |                |      |      |
|12 |J8         |PinHeader_1x02_P2.54mm_Vertical                 |1       |+5V            |                |      |      |
|13 |D2         |LED_D3.0mm                                      |1       |+12V           |                |      |      |
|14 |R1         |R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal|1       |12k            |                |      |      |
|15 |J5         |IDC-Header_2x08_P2.54mm_Vertical                |1       |E              |                |      |      |
|16 |J11        |IDC-Header_2x08_P2.54mm_Vertical                |1       |F              |                |      |      |
|17 |J12        |PinHeader_1x04_P2.54mm_Vertical                 |1       |Conn_01x04_Male|                |      |      |
|18 |J6         |PinSocket_1x08_P2.54mm_Horizontal               |1       |IO1            |                |      |      |
|19 |J7         |PinHeader_1x08_P2.54mm_Horizontal               |1       |IO2            |                |      |      |
