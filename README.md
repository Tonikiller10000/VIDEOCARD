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
After seing the Ben Eater Videocard series and some other videos about computers and how they work, I wanted to make a video card of my own, and I started building the <b> SCREEN SYNC</b>. Because of my limmited resources, I started making the parts of the videocard separatly. So I started making the 12 bit binnary counter on the breadboard ([video](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/ard_clk.mp4)) and after that, I made it on the [PCB](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t1.jpeg) at home. I used pins as vias, witch was very ugly but it worked [face](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t3.jpeg), [Back](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t2.jpeg)

<table>
  <tr>
    <td>
    Next, I wanted to make the modulse separated Hsync and Vsync [modules](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.3/t1.jpg), 
    witch I realised wasn\`t a very good idea, and I combined all the screen sync on one [board](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/s2.jpg). </td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/s3.jpg"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/s1.jpg"></td>
  </tr>
</table>

Than I tried a larger board to place the vias... 
<table>
  <tr>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.7/t2.jpg"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.7/t3.jpg"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.7/t4.jpg"></td>
  </tr>
</table>

So I dont entierly copy the design, I wantd to try making the latches with ne555 instead of NAND gates. Unfortunatly, I found out that the ne555 is not fast enouch for 10MHz and I switched back to the original design. Then because I couldn\`t place vias at home, I found about JLC pcb, and I made my first order...   V1.0 







## How to use the screen sync:
- (*) make programs for the switches in the arduinoIDE (max 8);
- connect a battery;
- turn the power of the shield down;


## Links:
74HC595 datasheet (shift register): https://datasheetspdf.com/pdf-file/446162/ONSemiconductor/74HC595/1



