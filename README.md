# VIDEOCARD

## Description:
This is an videocard made for my [8 bit computer]() witch I still work on. 

### Version V1.0
The [EEPROM Programmer V1.0](https://github.com/Tonikiller10000/EEPROM_PROGRAMER/blob/main/EEPROM_PROGRAMER_V1.0/EEPROM_PROGRAMER_V1.0_Pictures/20230729_093718.jpg) has only 2 smd shift registers used with and arduino on the breadboard to set the eeprom address at programming. With this programmer, the shift register connections ware already made so you don`t have to place 2 shift registers on breadboard, but because of the pins placement, it needed to be connected with jumper wires.




<table>
  <tr>
    <td>

### Pinout
- EEPROM Data pins
    - D0-D7     : Data EEPROM IO pins
- Shift Register control pins
    - CLK       : Shift Register CLK pin
    - LATCH     : Shift Register Latch pin
    - OE        : Shift Register OE pin
    - DataIn    : Shift Register Serial Data In pin
- EEPROM control pins
    - WE        : EEPROM Write Enable pin
    - OE        : EEPROM Output Enable pin
    - GND       : arduino GND
    - VCC       : arduino 5V
    </td>
    <td><img src="https://github.com/Tonikiller10000/EEPROM_PROGRAMER/blob/main/EEPROM_PROGRAMER_V2.0/EEPROM_PROGRAMER_V2.0_Pictures/EE2.jpg" width=300 height=400 ></td>
  </tr>
</table>




### Version V3.0
This design is an plug and play version. It is an arduino shield, with some extra power, pins and 4 smd dip switches with one power switch and 8 modes to program the eeprom on the go, without the need of an computer.
<table>
  <tr>
    <td><img src="https://github.com/Tonikiller10000/EEPROM_PROGRAMER/blob/main/EEPROM_PROGRAMER_V3.0/EEPROM_PROGRAMER_V3.0_Pictures/ee32.png" width=300 height=200 ></td>
    <td><img src="https://github.com/Tonikiller10000/EEPROM_PROGRAMER/blob/main/EEPROM_PROGRAMER_V3.0/EEPROM_PROGRAMER_V3.0_Pictures/ee31.png" width=300 height=200 ></td>
    <td><img src="https://github.com/Tonikiller10000/EEPROM_PROGRAMER/blob/main/EEPROM_PROGRAMER_V3.0/EEPROM_PROGRAMER_V3.0_Pictures/ee33.png" width=300 height=200 ></td>
  </tr>
</table>




## History

After seing the Ben Eater Videocard series and some other videos about computers and how they work, I wanted to make a video card of my own, and I started building the <b> SCREEN SYNC</b>. Because of my limmited resources, I started making the parts of the videocard separatly. So I started making the 12 bit binnary counter on the breadboard ([video]()) and after that, I made it on the [PCB](t1) at home. I used pins as vias, witch was very ugly but it worked [face](t3), [Back](t2)

Next, I wanted to make the modulse separated ([Hsync]() and [Vsync]()), witch I realised wasn\`t a very good idea, and I combined all the screen sync on one [board](s2).    table s3,s1

Than I tried a larger board to place the vias...  table,t2,t3,t4

So I dont entierly copy the design, I wantd to try making the latches with ne555 instead of NAND gates. Unfortunatly, I found out that the ne555 is not fast enouch for 10MHz and I switched back to the original design. Then because I couldn\`t place vias at home, I found about JLC pcb, and I made my first order...   V1.0 







## How to use:
- (*) make programs for the switches in the arduinoIDE (max 8);
- connect a battery;
- turn the power of the shield down;



## Programming:
[This](https://github.com/Tonikiller10000/EEPROM_PROGRAMER/blob/main/EEPROM_PROGRAMER_V2.0/EEPROM_PROGRAMER_V2.0.ino) code is made for the EEPROM V1.0 and V2.0. The software for the version 3.0 has permanent pins and  will be made when the board arrives.



## Links:
74HC595 datasheet (shift register): https://datasheetspdf.com/pdf-file/446162/ONSemiconductor/74HC595/1
AT28C256 datasheet (32K EEPROM): https://ww1.microchip.com/downloads/en/DeviceDoc/doc0006.pdf
AT28C64 datasheet (8K EEPROM): https://ww1.microchip.com/downloads/en/devicedoc/doc0001h.pdf


