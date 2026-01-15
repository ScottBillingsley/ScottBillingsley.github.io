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

## Editor

I have gotten all the functions working except the disconnect serial.
The features as of now:
___		

-  Load Project:&emsp; Loads a saved porject
-  Save Project: &emsp; Saves all data entered in the main txt area
-  Save HEX file: &emsp; Saves all HEX data as 0x##, 0x##, for use in a byte array
-  New:	&emsp; 	&emsp;	Clears the text area
-  Serial: &emsp;	Set the port, baud, connect and disconnect
-  Upload: &emsp; Upload the HEX data in the text area as binary bytes.
-  Navigate: &emsp; Jumps to an address. 
-  Help: &emsp; &emsp;	Popup a free standing window with the Chip8 opcodes
- 	Flowchart maker: &emsp;	Make, Save and Load simple flowcharts

                    