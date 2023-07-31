# Merp

Modular Eurorack Powerbus (Merp) is yet another power bus [KiCad](https://www.kicad.org/) project. Yes, we're truly breaking new ground here... This has never been done before. Ahem.

## Never been done before, eh?

OK. I may have started with [Eurorack Bus Board](https://github.com/butchwarns/Eurorack_Bus_Board) by Butch Warns. I was going to just order it but it was too wide for the cheap PCB fabrications. I think I iterated on his work enough to call this its own thing.

## Why Merp?

I think the only differentator with Merp from the other power bus PCBs is that Merp is designed to be ordered from one of the Chinese PCB fabs for their minimum price. [PCBWay](https://www.pcbway.com/) for example currently has 5 boards for $5 if they're under 100mm x 100mm which Merp qualifies for.

There are 6 power bus connectors per board. If you order 5 boards you can connect them all together and have 30 x 16 pin Doepfer sockets (I hope you have at least 104 hp rails if you're doing that) 

This board rquires +12V, -12V and +5V supplies. I'm using [Meanwell RT-65](https://www.meanwell.com/webapp/product/search.aspx?prod=RT-65) to power mine. The board has no +5V conversion and performs no power regulation. If none of your Eurorack modules use +5V you can get away without it.

Use a tested power supply. Before connecting any of your Eurorack modules, power up just the bus board. Ensure the LEDs are lit. Ensure that the correct voltages present.

# Renders

Here's some pictures of the board that KiCad generated.

## Front

![](images/merp_front.png?raw=true)

## Front Again

![](images/merp_front2.png?raw=true)

The red line on Eurorack module power connectors are to be installed towards the bottom of the board as indicated although this should be enforced by the IDC connector notches.

## Back

![](images/merp_back.png?raw=true)

# Notes

- The resistor values are just a starting point. I find the +12 LED to be too bright and the +5 to be too dim with these values. They're simply there to make the power indicator LEDs a bit dimmer.
- The LEDs and the pin headers below them are the same thing. If you're connecting an LED via a header, ensure the positive leg connects to the + pin (note the pad shapes are opposite for the -12V led, the cathode is on the same side when mounted though.)
- If you don't want to use the LEDs you can leave the resistors, LEDs and associated headers unpopulated. They are not required for operation of the power bus.
- The interconnect header & socket are shown to be mounted on the back on the boards. The boards are intended to be installed in your Eurorack case on standoffs. The board should be about 5mm bigger in that dimension for this reason (it might make sense to make the whole board twice as tall to allow for staggering of the connectors as they're pretty tight)
- If you don't want to connect a module to the left or right, leave the interconnect header or socket unpopulated.
- There's an additional power header on the left side of the board. This header is entirely optional. A future revision will likely make this a screw terminal instead of a pin header.
- You can probably only populate the filter capacitors on one of your boards. Or none of them... They're optional.
- All signals are passed through all interconnected power bus modules.
- The Gate and CV lines of the Doepfer bus are connected, inclusive of module interconnects.
- The mounting holes are suitable for M3 bolts & standoffs.

# BOM

All parts are THT.

|Designator|Package|Quantity|Designation|
|-|-|-|-|
|R1|Axial Resistor 1/4W |1|12k*|
|R2,R3|Axial Resistor 1/4W|2|47k*|
|J1,J2,J3,J4,J5,J10,J11|16 Pin Eurorack Power Male|6|A,B,C,D,E,F|
|C3,C2,C1|Electrolytic Capactior|3|47uF|
|D1,D2,D3|3mm LED|1|+5V,+12V,-12V|
|J8,J9,J10|Pin Header 1x2 2.54mm Pitch Vertical|3|+5V,+12V,-12V|
|J12|Pin Connector 1x4 2.54mm Pitch|1||
|J6|Pin Socket 1x8 2.54mm Pitch Horizontal|1|IO1|
|J7|Pin Header 1x8 2.54mm Pitch Horizontal|1|IO2|
