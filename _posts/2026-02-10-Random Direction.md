## Random Direction

A code example of generationing random numbers of
2, 4, 6, or 8 used for random directions.

```cpp
//  Random Direction
//  Vernon Billingsley c2026
00E0	// CLS
611D	// LD V1, 1D
620D	// LD V2, 0D
# Random dir  2 = UL 4 = UR
#	          6 = DL 8 = DR
C007	// V0 = RND & 07
6AFE	// LD VA, FE
80A2	// AND V0, VA
7002	// ADD V0, 02
F029	// LD F, V0
D125	// DRW V1, V2, 5
F00A	// LD V0, K
D125	// DRW V1, V2, 5
1206	// JP 206
```

You can use it to set directions like this..

```cpp
# Next Step
4302	// SNE V3, 02
128C	// JP 28C
4304	// SNE V3, 04
1286	// JP 286
4306	// SNE V3, 06
1280	// JP 280
# 8 = DR
7101	// ADD V1, 01
7201	// ADD V2, 01
00EE	// RET
# 6 = DL
71FF 	// ADD V1, FF
7201	// ADD V2, 01
00EE	// RET
# 4 = UR
7101	// ADD V1, 01
72FF	// ADD V2, FF
00EE	// RET
# 2 = UL
71FF	// ADD V1, FF
72FF	// ADD V2, FF
00EE	// RET
```



