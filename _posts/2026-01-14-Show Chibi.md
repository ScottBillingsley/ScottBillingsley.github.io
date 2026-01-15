## My Chibi

I decided to write a simple program to display my chibi.,,

![]({{site.baseurl}}/images/chip8/Chibi.png)

I used my editor..

![]({{site.baseurl}}/images/chip8/Show Chibi.png)

With a new added freature. I added a simple flowchart..

![]({{site.baseurl}}/images/chip8/ShowChibi.png)

Because I'm hand programming, I've set the program up a little 
diferent. I start with setting the registers. The data in entered
next, or it could be a timer or a keyboard check, I then do a 
jump to the program. This way I can know the address to data or for
a call routine without having to change it everytime I enter something
new..

``` asm
// Display Chibi
6000	// v0 = 0	
6108	// v1 = 8	 Start X
6200	// v2 = 0	 Start Y
6308	// v3 = 8	 Add amount
6400 	// v4 = 0  X byte count
6500    // v5 = 0 	Y byte count
00E0	// Clear the screen
1290	// Jump to program
#  Data
0000
0101
0303
0306
//
1F71
C000
0000
0000
//
00C0
6030
1018
1818
//
0000
0000
0000
0000
//	Row 2
070C
0C06
0203
0000
//
718E
8A71
000F
F06F
//
DC2C
2CC8
1810
2040
//
0000
0000
0000
0000
//	Row 3
0000
0102
0408
0502
//
1D2F
CF00
017E
8000
//
8060
10F8
0506
6362
//
0C12
1264
9860
8000
//	Row 4
0404
0402
0102
0204
//
0020
1000
01C2
3C00
//
0206
18E8
0400
0804
//
0000
0000
0000
0000
# Program
A210		// Set i to start of data
D128		// Display 8 bytes at v1, v2
F31E		// Add 8 to i
8134		// Add 8 to X
7401		// Add 1 to X counter
3404		// Skip next if == 4
1292		// Jump to display
6400		// Clear X counter
6108		// Set x pos to start
8234		// Add 8 to Y
7501		// Add 1 to Y counter
3504		// Skip next if == 4
1292		// Jump to display
12AA		// Loop

```

## Editor

I have gotten all the functions working except the disconnect serial.<br>
The features as of now:<br>

-  Load Project: &emsp; Loads a saved porject
-  Save Project: &emsp; Saves all data entered in the main txt area
-  Save HEX file:  &ensp; Saves all HEX data as 0x##, 0x##, for use in a byte array
-  New:	&emsp; &emsp; &emsp; &ensp;&ensp;&ensp;Clears the text area
-  Serial: &emsp; &emsp; &ensp; &ensp; &ensp;Set the port, baud, connect and disconnect
-  Upload: &emsp; &emsp; &ensp; &ensp; Upload the HEX data in the text area as binary bytes.
-  Navigate: &emsp;&ensp;&ensp;&ensp;&ensp; Jumps to an address. 
-  Help:&ensp; &emsp;&emsp;&ensp; &ensp; &ensp; &ensp;Popup a free standing window with the Chip8 opcodes
-  Flowchart:&emsp;&ensp;&ensp; &ensp; &ensp;Make, Save and Load simple flowcharts
