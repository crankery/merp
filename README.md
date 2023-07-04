# Merp

🛑 This is untested. Do not build this thing. I will post an update when it's been tested.

Modular Eurorack Powerbus (Merp) is yet another power bus KiCad project. Yes, we're truly breaking new ground here... This has never been done before.

I think the only differentator with this from the other power bus PCBs is that this one is designed to be ordered from one of the Chinese PCB fabs for their minimum price. The width of the board is 100mm while the height is much less than that. [PCBWay](https://www.pcbway.com/) for example currently has 5 boards for $5 if they're under 100mm x 100mm. If you order 5 boards you can connect them all together and have 30 x 16 pin Doepfer sockets (I hope you have 104 hp rails if you're doing that). 

This board rquires +12V, -12V and +5V supplies. I'm using [Meanwell RT-65](https://www.meanwell.com/webapp/product/search.aspx?prod=RT-65) to power mine. The board has no +5V conversion and does no power regulation. If none of your Eurorack modules use +5V you can get away without it.

The mounting holes are suitable for M3 bolts & stand offs. Standard through hole components are exclusively used.  

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
- The LEDs or the pin headers below them are the same thing. This is to allow the LEDs to be put on a front panel if desired. If you don't want to use the LED on a board you can leave the resistors, LEDs and associated headers off your board. They are not required for operation of the power bus.
- The interconnect header & socket are shown on the back on the board. The boards are intended to be installed in your Eurorack case on M3 standoffs. If you don't want to connect a module to the left, leave that header off. If you don't want to connect a module on the right, leave the socket off.
- There's an additional power header on the left side of the board. This is optional. You could power it from the left or right interconnect as well.
- The 3 capactiors are there because the project this was based on had them. I guess they're supposed to do some filtering. They probably only need to be present on one module if at all. The bus will work without them being present.
- All signals are passed through all interconnected power bus modules.
- The Gate & CV lines of the Doepfer bus are connected, inclusive of module interconnects.
