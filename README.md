# VIDEOCARD

## Description:
This is an videocard made for my [8 bit computer]() witch I still work on. It should be able to display graphics, texts and pictures on all tipes of screens and diplays. 

## How VGA monitors works
The vga screen works by reciving analog signals between 0 and 0.7V for every collor at specific pixel position to set the separate color intensity of the red,green and blue collors at that pixel. 
Also, to set the screen resolution and speed, 2 aditional SYNC signals are sented at very precise time intervals at the end of every line(HSYNC) and every screen(VSYNC) in witch time, no collor is sent/displayed

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
  <tr><td>9</td>            <td>+5V</td>    <td>--></td>    <td>+5 VDC (optional)</td></tr>
  <tr><td>10</td>           <td>SGND</td>   <td>---</td>    <td>Sync Ground</td></tr>
  <tr><td>11</td>           <td>ID0</td>    <td><--</td>    <td>Monitor ID Bit 0 (optional)</td></tr>
  <tr><td>12</td>           <td>SDA</td>    <td><-></td>    <td>DDC Serial Data Line</td></tr>
  <tr><td>13</td>  <td>HSYNC or CSYNC</td>  <td>--></td>    <td>Horizontal Sync (or Composite Sync)</td></tr>
  <tr><td>14</td>           <td>VSYNC</td>  <td>--></td>    <td>Vertical Sync</td></tr>
  <tr><td>15</td>           <td>SCL</td>    <td><-></td>    <td>DDC Data Clock Line</td></tr>
</table>
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/port.png">
Learn more about [VGA pins](https://pinoutguide.com/Video/VGA15_pinout.shtml)<br>

<details> <summary>How screen SYNC works</summary>
<br>
To select the VGA screen resolution and speed, you need to chose one [VGA mode](http://tinyvga.com/vga-timing), and sent the specific signals at the rigth time.
Because of the convenience, I also used the 800x600 px resolution at 60Hz witch uses a 40 MHz pixel frequency. By looking on the timing chart, it\`s seems that the timing can be devided by 4 witch will result in a pixel size of 4 actual pixels on a row at a resolution of 200x600 px but with a clk speed of 10MHz. For the beauty of it, by writing the same pixels collors every 4 rows, the screen can display 200x150 px resolution with a pixel beeing actually 4x4 px. 

### SVGA Signal 800x600 @ 60Hz timing

#### General timing
<table>
  <tr><td>Screen refresh rate   </td><td>60 Hz</td></tr>      
  <tr><td>Vertical refresh      </td><td>37.878787878788 kHz</td></tr>  
  <tr><td>Pixel freq.           </td><td>40.0 MHz</td></tr>   
  <tr><td>Used Pixel freq.      </td><td>10.0 MHz</td></tr>   
</table>

#### Horizontal timing (line)
<table>
  <tr><td>Scanline part</td> <td>Pixels</td> <td>Time [us]</td> <td>Used Pixels</td> <td>Reached Pixel</td> <td>Binnary</td>    </tr>
  <tr><td>Visible area</td>  <td>800</td>    <td>20</td>        <td>200</td>         <td>200</td>           <td>0 1100 1000</td></tr>
  <tr><td>Front porch</td>   <td>40</td>     <td>1</td>         <td>10</td>          <td>210</td>           <td>0 1101 0010</td></tr>
  <tr><td>Sync pulse</td>    <td>128</td>    <td>3.2</td>       <td>32</td>          <td>242</td>           <td>0 1111 0010</td></tr>
  <tr><td>Back porch</td>    <td>88</td>     <td>2.2</td>       <td>22</td>          <td>264</td>           <td>1 0000 1000</td></tr>
  <tr><td>Whole line</td>    <td>1056</td>   <td>26.4</td>      <td>264</td>         <td>   </td>           <td></td>           </tr>
</table>

#### Vertical timing (frame)
<table>
  <tr><td>Frame part</td>   <td>Lines</td> <td>Time [us]</td> <td>Used Lines</td> <td>Reached Line</td> <td>Binnary</td>      </tr>
  <tr><td>Visible area</td> <td>600</td>   <td>15.84</td>     <td>600</td>        <td>600</td>          <td>10 0101 1000</td> </tr>
  <tr><td>Front porch</td>  <td>1</td>     <td>0.0264</td>    <td>1</td>          <td>601</td>          <td>10 0101 1001</td> </tr>
  <tr><td>Sync pulse</td>   <td>4</td>     <td>0.1056</td>    <td>4</td>          <td>605</td>          <td>10 0101 1101</td> </tr>
  <tr><td>Back porch</td>   <td>23</td>    <td>0.6072</td>    <td>23</td>         <td>628</td>          <td>10 0111 0100</td> </tr>
  <tr><td>Whole frame</td>  <td>628</td>   <td>16.5792</td>   <td>628</td>        <td>   </td>          <td></td>             </tr>
</table>

<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/screen.png">
</details>

<details> <summary>How the board works</summary>
<br>

The videocard has 2x 12bit binnary counter, each made of 3x 4bit binnary counter(74LS161), witch count the displayable row and pixel on that row. The counted value is modified with some inverters(74LS04) at specified bits and outputed to some 8 inputs NAND gates(74LS30) to detect when the counter arrived at some specified numbers. The NAND gates set and reset 4 latches made with other type of NAND gates(74LS00), whose outputs indicate the HSYNC, VSYNC, VBLANK and HBLANK. The SYNC signals are dirrectly sent to the VGA port pins, and the BLANK signals indicate when to sent the collor values and when not to.

</details>








## History:
After seing the Ben Eater Videocard series and some other videos about computers and how they work, I wanted to make a video card of my own, and I started building the <b> SCREEN SYNC</b>. Because of my limmited resources, I started making the parts of the videocard separatly. So I started making the 12 bit binnary counter on the breadboard ([video](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/ard_clk.mp4)) and after that, I made it on the [PCB](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t1.jpeg) at home. I used pins as vias, witch was very ugly but it worked ([face](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t3.jpeg), [Back](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.2/t2.jpeg))
Next, I wanted to make the modulse separated Hsync and Vsync [modules](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.3/t1.jpg), 
and when I realised wasn\`t a very good idea, and I combined the screen sync parts on one [board](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/s2.jpg) witch needed to be [double sided](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.7/t2.jpg) and very lartge to place the vias(this was the largest size). 

#### version 0.6
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V0.6/ss.jpg " height = 400 >

So I dont entierly copy the design, I wantd to try making the latches with ne555 instead of NAND gates. Unfortunatly, I found out that the ne555 is not fast enouch for 10MHz and I switched back to the original design. 

#### Version 1.0
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V1.0/t2.jpg" height = 400 >

Because I couldn\`t place vias at home, I found about [JLC pcb](https://jlcpcb.com/), and I made my first order.    
For this order, I needed to change the software I was working with and I found the open source software KICAD, witch I didn`t know at the time how to fully use with the DRC and other stuff. 
I staied few months to work at it not knowing the wanted final design, and because I was tired and bored of it, I ordered fast without checking it carefully.
When testing, it didn\`t work and after few weeks f break, I saw that the bus was wired again and I ordered it again with a new pin design and a very carefully check.

#### Version 2.0
After [many](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/try.png) design considerations, the [board](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r8.png) was [working](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/rez.png).

<table>
  <tr>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r7.png" height = 300 width= 300 ></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/p.png"  height = 300 width= 300 ></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r5.jpg" height = 300 width= 300 ></td>
  </tr>
</table>

#### Schematic:
<img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/s1.png">


## How to use:
- power the board to 5V
- connect the VGA port to the monitor
- tie the HBLANK and VBLANK signals to a NAND gate (74LS00) to make the BLANK signal (active HIGH)
- send analog voltages(0V-0.7V) to the analog color pins 

<details> <summary><b>Screen SYNC Pinout</b></summary>
<table>
  <tr><td>Pins</td>       <td>Type</td>                     <td>Description</td></tr>
  <tr><td>H0-H7</td>      <td>OUTPUT</td>                   <td>indicate the pixel position on the line (H7 MSB)</td> </tr>
  <tr><td>V0-V7</td>      <td>OUTPUT</td>                   <td>indicate the row position on the screen (V7 MSB)</td> </tr>
  <tr><td>VCC</td>        <td>POWER INPUT</td>              <td>5V POWER INPUT </td> </tr>
  <tr><td>GND</td>        <td>POWER INPUT</td>              <td>0V POWER INPUT </td> </tr>
  <tr><td>CLK</td>        <td>INPUT/OUTPUT</td>             <td>output cristal output if placed (recomanded) or crystal input if not</td>  </tr> 
  <tr><td>CLK4</td>       <td>INPUT</td>                    <td>for cristals with enable pin</td>  </tr>
  <tr><td>VGA1BLUE</td>   <td>ANALOG INPUT (0V-0.7V)</td>  <td> blue ligth intensity of the current pixel on VGA1 monitor</td>  </tr>
  <tr><td>VGA1GREEN</td>  <td>ANALOG INPUT (0V-0.7V)</td>  <td> green ligth intensity of the current pixel on VGA1 monitor</td>  </tr>
  <tr><td>VGA1RED</td>    <td>ANALOG INPUT (0V-0.7V)</td>  <td> red ligth intensity of the current pixel on VGA1 monitor</td>  </tr>
  <tr><td>VGA2BLUE</td>   <td>ANALOG INPUT (0V-0.7V)</td>  <td> blue ligth intensity of the current pixel on VGA2 monitor</td>  </tr>
  <tr><td>VGA2GREEN</td>  <td>ANALOG INPUT (0V-0.7V)</td>  <td> green ligth intensity of the current pixel on VGA2 monitor</td>  </tr>
  <tr><td>VGA2RED</td>    <td>ANALOG INPUT (0V-0.7V)</td>  <td> red ligth intensity of the current pixel on VGA2 monitor</td>  </tr>
  <tr><td>HBLANK</td>     <td>OUTPUT</td>                   <td>LOW if the drawn pixel is in the displayable area of the row</td> </tr>
  <tr><td>VBLANK</td>     <td>OUTPUT</td>                   <td>LOW if the drawn row is in the displayable area of the screen</td> </tr>
</table>
</details>

<details> <summary><b>connecting it to memory</b></summary>

When connected to the 32K EEPROM(AT24C256), the data pins will have each 2 an 680 ohm and an 1.5 Kohm resistors to make [4 voltage points between 0V and 0.7V](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/vvv.png).
Because of the HIGH display speed, it is possible the aparition of some artifacts on the screen.
To save a picture in the memory, the picture dimmension is reduced to 100x75px, the number of collors and shades is reduced(4 red shades x 4 green shades x 4 blue shades = 64 collor shades) and the picture binnary file is moddified and copied to the EEPROM. Also the enable pin must be LOW to display the picture, and HIGH when the SYNC signals are sent. The HBLANK and VBLANK signals are outputed in a NAND gate (74LS00) witch make the BLANK signal active HIGH, and for the EEPROM it is inverted again by passing again trouth the gate with both inputs tied together.
<br> Also by connecting a processor, microcontroller or another processing circuit, you can make 

[moving models](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/e2.png) and dynamic screens.
<table>
  <tr>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/bird.png" height = 300 width= 300 ></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/8clo.png" height = 300 width= 300 ></td>
    <td><img src="https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/General/e1.png"   height = 300 width= 300 ></td>
  </tr>
</table>
</details>


## Conclusion:
The board is partially tested without being connected to the memory, because of the missing EEPROM programmer at the moment of testing
I wanted to use 2 monitors simultanely, But unfortunately, the ports are [too close too each other](https://github.com/Tonikiller10000/VIDEOCARD/blob/main/VIDEOCARD_Pictures/V2.0/r4.jpg).
Now I will try to tie 3 RAM memory\`s(one for each collor) to make 255x255x255 color shades.

## Datasheets:
- 74LS00 (NAND gate):https://pdf1.alldatasheet.com/datasheet-pdf/view/51021/FAIRCHILD/74LS00.html
- 74LS04 (Inverter):https://pdf1.alldatasheet.com/datasheet-pdf/view/5638/MOTOROLA/74LS04.html
- 74LS30 (8 bit NAND gate):https://pdf1.alldatasheet.com/datasheet-pdf/view/12613/ONSEMI/74LS30.html
- 74LS161 (binnary counter):https://pdf1.alldatasheet.com/datasheet-pdf/view/5675/MOTOROLA/74LS161.html

## External Links:
- VGA pins: https://pinoutguide.com/Video/VGA15_pinout.shtml
- VGA resolutions: http://tinyvga.com/vga-timing
- BenEater YouTube: https://www.youtube.com/beneater
- BenEater WebSite: https://eater.net/vga
- JLC PCB: https://jlcpcb.com/ 
