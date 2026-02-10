## Step Control

An example of controlling direction change using one register.

```cpp

//   Negative Test
//  How to change directions using 
// on register
# registers  v0 temp v1 X  v2 Y
# v3 count  v4 timer 
6000	// LD V0, 00
6100	// LD V1, 00
6210	// LD V2, 10
6301	// LD V3, 01
6406	// LD V4, 06
1236	// JP 236
# data
40A0	// SNE V0, A0
4000	// SNE V0, 00
# timer
F415	// LD DT, V4
F007	// LD V0, DT
4000	// SNE V0, 00
00EE	// RET
1212	// JP 212
# Step control
3301	// SE V3, 01
122A	// JP 22A
8134	// ADD V1, V3
413D	// SNE V1, 3D
1226	// JP 226
00EE	// RET
63FF	// LD V3, FF
00EE	// RET
8134	// ADD V1, V3
4100	// SNE V1, 00
1232	// JP 232
00EE	// RET
6301	// LD V3, 01
00EE	// RET
# program
00E0	// CLS
A20C	// LD I, 20C
D123	// DRW V1, V2, 3
2210	// CALL 210
D123	// DRW V1, V2, 3
221A	// CALL 21A
123A	// JP 23A
```

Also an example of placing data and timers first and jumping
to the start of the program to make hand programming eaiser
because the jump addrees doesn't change.
