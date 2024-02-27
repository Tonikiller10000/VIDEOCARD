# VIDEOCARD

## Description:
This is an videocard made for my [8 bit computer]() witch I still work on. 






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





## History
After seing the Ben Eater Videocard series and some other videos about computers and how they work, I wanted to make a video card of my own, and I started building the <b> SCREEN SYNC</b>. Because of my limmited resources, I started making the parts of the videocard separatly. So I started making the 12 bit binnary counter on the breadboard ([video](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/ard_clk.mp4)) and after that, I made it on the [PCB](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t1.jpeg) at home. I used pins as vias, witch was very ugly but it worked ([face](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t3.jpeg), [Back](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t2.jpeg))
Next, I wanted to make the modulse separated Hsync and Vsync [modules](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.3/t1.jpg), 
and when I realised wasn\`t a very good idea, and I combined the screen sync parts on one [board](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/s2.jpg) witch needed to be [double sided](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.7/t2.jpg) and very lartge to place the vias(this was the largest size). 

### version 0.6
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/ss.jpg " height = 400 >

So I dont entierly copy the design, I wantd to try making the latches with ne555 instead of NAND gates. Unfortunatly, I found out that the ne555 is not fast enouch for 10MHz and I switched back to the original design. Then because I couldn\`t place vias at home, I found about JLC pcb, and I made my first order:     

### Version 1.0
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V1.0/t2.jpg" height = 400 >
For this order, I needed to change the software, and I found the open source software KICAD, witch I didn`t know at the time how to fully use with the DRC and stuff, 
Because I didn`t know the final design I wanted, I staied few months to work at it, and because I was tired and bored of it, I ordered fast without checking it carefully.
When testing, it didn\`t work and after few weeks f break, I saw that the bus was wired again and I ordered it again with a new pin design and a very carefully check.

### Version 2.0
After [many](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/try.png) design considerations, the board was working.

<table>
  <tr>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/p.png"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r4.jpg"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r5.jpg"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r7.png"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r8.png"></td>
  </tr>
</table>

### Schematic
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/s1.png">

<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/8clo.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/ana.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/bird.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/e1.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/e2.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/port.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/res.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/rez.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/rez2.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/rezz.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/screen.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/vvv.png">









## How to use the screen sync:
- (*) make programs for the switches in the arduinoIDE (max 8);
- connect a battery;
- turn the power of the shield down;


## Links:
74HC595 datasheet (shift register): https://datasheetspdf.com/pdf-file/446162/ONSemiconductor/74HC595/1



