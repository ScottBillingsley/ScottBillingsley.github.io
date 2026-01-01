## Welcome to my blog. 
  
  Here I will post about my efforts to write a CHIP8 emulator.
  I have already developed the core portion of the emulator and 
  I'm now in the process of reworking and improving. I'm also 
  doing some redesigns looking ahead at additions I want to include,
  such as an IO port, better sound and basic operating system.
  
  __How it started__
 	
  In early 2025 I was looking around for a 5v microcontoller to use
  on a project for my modular synth. The teensy LC was gone from the
  market and most all other high speed contorllers were 3.3 volt. I
  had played around with Microchip's Curiosity Nano so I decided to 
  develope my own microcontroller based on the AVR128DB48. This is 
  the results.
 
![AVRDuino Eddie.png]({{site.baseurl}}/images/AVRDuino Eddie.png)

  It has 128k of ram, 16k of sram, a footprint for a at28c256 or at28c512
  eeprom on Wire0 and a 3.3 or 5 volt MVIO port on PORTC. While the datasheet
  has a max speed of 20 mHz, they a capable of a lot of over clocking. I 
  run this version at 40 mHz but have a version in a video card running at
  48 mHz.
  
  __Concept__
  
  This is the general layout of the CHIP8 emulator.
 
 ![CHIP8 Concept 2.png]({{site.baseurl}}/images/CHIP8 Concept 2.png)

  The video card is updated on the horizontal sync pulse and is able to
  send 4 bytes per pulse. 60 fps is easily achieved in both standard
  resolution of 64x32 and high resolution of 128x64. There will also 
  be text mode for use with an os. The keyboard will access the data
  bus in between the sync pulses. At a later time, I plan for an IO
  port to work the same.
  
  Information on the AVRduino Eddie, along with artwork for Kicad 7
  and code sippets can be found on my github under Philosophy of Noise
  repository. There is also info on several modules I designed for my
  modular synth and some fun starvation tube circuits.
  
  All my programming is done using arduino 1.8.19, as recomended by
  Spencer Konde for [DxCore](https://github.com/SpenceKonde/DxCore/tree/master).
  My OS is [MX Linux](https://mxlinux.org/).
