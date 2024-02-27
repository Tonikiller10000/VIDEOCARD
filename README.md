# VIDEOCARD

## Description:
This is an videocard made for my [8 bit computer]() witch I still work on. 






## SVGA Signal 800x600 @ 60Hz timing

### General timing
<table>
  <tr><td>Screen refresh rate   </td><td>60 Hz</td></tr>      
  <tr><td>Vertical refresh      </td><td>37.878787878788 kHz</td></tr>  
  <tr><td>Pixel freq.           </td><td>40.0 MHz</td></tr>   
  <tr><td>Used Pixel freq.      </td><td>10.0 MHz</td></tr>   
</table>

### Horizontal timing (line)
<table>
  <tr><td>Scanline part</td> <td>Pixels</td> <td>Time [us]</td> <td>Used Pixels</td> <td>Reached Pixel</td> <td>Binnary</td> </tr>
  <tr><td>Visible area</td>  <td>800</td>    <td>20</td>        <td>200</td> <td>200</td>  <td>0 1100 1000</td> </tr>
  <tr><td>Front porch</td>   <td>40</td>     <td>1</td>         <td>10</td>  <td>210</td>  <td>0 1101 0010</td> </tr>
  <tr><td>Sync pulse</td>    <td>128</td>    <td>3.2</td>       <td>32</td>  <td>242</td>  <td>0 1111 0010</td> </tr>
  <tr><td>Back porch</td>    <td>88</td>     <td>2.2</td>       <td>22</td>  <td>264</td>  <td>1 0000 1000</td> </tr>
  <tr><td>Whole line</td>    <td>1056</td>   <td>26.4</td>      <td>264</td> <td>   </td>  <td></td> </tr>
</table>













## VGA Port Pinout
<table>
  <tr><td>Pin number</td>   <td>Name</td>   <td>Dir</td>    <td>Description</td></tr>
  <tr><td>1</td>            <td>RED</td>    <td>--></td>    <td>Red Video(75 ohm, 0.7V)</td></tr>
  <tr><td>2</td>            <td>GREEN</td>  <td>--></td>    <td>Green Video(75 ohm, 0.7V)</td><tr>
  <tr><td>3</td>            <td>BLUE</td>   <td>--></td>    <td>Blue Video(75 ohm, 0.7V)</td></tr>
  <tr><td>4</td>            <td>RES</td>    <td>   </td>    <td>Reserved</td></tr>
  <tr><td>5</td>            <td>GND</td>    <td>---</td>    <td>Ground</td></tr>
  <tr><td>6</td>            <td>RGND</td>   <td>---</td>    <td>Red Ground</td></tr>
  <tr><td>7</td>            <td>GGND</td>   <td>---</td>    <td>Green Ground</td></tr>
  <tr><td>8</td>            <td>BGND</td>   <td>---</td>    <td>Blue Ground</td></tr>
  <tr><td>9</td>            <td>+5V</td>    <td>--></td>    <td>+5 VDC</td></tr>
  <tr><td>10</td>           <td>SGND</td>   <td>---</td>    <td>Sync Ground</td></tr>
  <tr><td>11</td>           <td>ID0</td>    <td><--</td>    <td>Monitor ID Bit 0 (optional)</td></tr>
  <tr><td>12</td>           <td>SDA</td>    <td><-></td>    <td>DDC Serial Data Line</td></tr>
  <tr><td>13</td>  <td>HSYNC or CSYNC</td>  <td>--></td>    <td>Horizontal Sync (or Composite Sync)</td></tr>
  <tr><td>14</td>           <td>VSYNC</td>  <td>--></td>    <td>Vertical Sync</td></tr>
  <tr><td>15</td>           <td>SCL</td>    <td><-></td>    <td>DDC Data Clock Line</td></tr>
</table>




## History
After seing the Ben Eater Videocard series and some other videos about computers and how they work, I wanted to make a video card of my own, and I started building the <b> SCREEN SYNC</b>. Because of my limmited resources, I started making the parts of the videocard separatly. So I started making the 12 bit binnary counter on the breadboard ([video](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/ard_clk.mp4)) and after that, I made it on the [PCB](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t1.jpeg) at home. I used pins as vias, witch was very ugly but it worked ([face](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t3.jpeg), [Back](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t2.jpeg))
Next, I wanted to make the modulse separated Hsync and Vsync [modules](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.3/t1.jpg), 
and when I realised wasn\`t a very good idea, and I combined the screen sync parts on one [board](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/s2.jpg) witch needed to be [double sided](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.7/t2.jpg) and very lartge to place the vias(this was the largest size). 

### version 0.6
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/ss.jpg " height = 400 >

So I dont entierly copy the design, I wantd to try making the latches with ne555 instead of NAND gates. Unfortunatly, I found out that the ne555 is not fast enouch for 10MHz and I switched back to the original design. 

### Version 1.0
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V1.0/t2.jpg" height = 400 >

Because I couldn\`t place vias at home, I found about JLC pcb, and I made my first order.    
For this order, I needed to change the software I was working with and I found the open source software KICAD, witch I didn`t know at the time how to fully use with the DRC and other stuff. 
I staied few months to work at it not knowing the wanted final design, and because I was tired and bored of it, I ordered fast without checking it carefully.
When testing, it didn\`t work and after few weeks f break, I saw that the bus was wired again and I ordered it again with a new pin design and a very carefully check.

### Version 2.0
After [many](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/try.png) design considerations, the [board](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r8.png) was working.

<table>
  <tr>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/p.png"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r5.jpg"></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r7.png"></td>
  </tr>
</table>

### Schematic
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/s1.png">

<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/8clo.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/bird.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/e1.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/e2.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/port.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/res.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/rez.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/rez2.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/screen.png">
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/vvv.png">





After fully assembly and testing of the board, I wanted to use 2 monitors simultanely, But unfortunately, the ports are [too close too each other](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r4.jpg).



## How to use the screen sync:
- (*) make programs for the switches in the arduinoIDE (max 8);
- connect a battery;
- turn the power of the shield down;


## Links:
74HC595 datasheet (shift register): https://datasheetspdf.com/pdf-file/446162/ONSemiconductor/74HC595/1



