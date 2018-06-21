# PBIN file format research

CS:GO finally implemented Panorama on 2018-06-19, and with it `Counter-Strike Global Offensive\csgo\panorama\code.pbin` was
created.  
Its contents can be extracted just like a ZIP file, but trying to reassemble or hex edit it causes a runtime error when
launching CS:GO.

To date, two versions of the file have been analyzed.

---

# PBIN header

The header contains 516 bytes.  
The first 4 bytes have always been `50 41 4e 01` so far (PAN, for Panorama, and 01 is probably the file version).
No other consistencies between versions were observed. 

### 2018-06-20 PBIN HEADER
```
50 41 4e 01 94 f3 11 27 76 4d dc 50 94 a7 4b cb
d7 ec 3c 0b b8 09 82 87 09 64 f1 65 5e 71 42 2c
44 f4 cc f2 c1 6c 53 7e b9 cd 52 7f f3 0c a0 29
fe 9f ce 81 af fa 13 20 7c 06 ad c3 4b c0 ec 0c
26 bd 8f 5f b4 6c ad 7d 1b 03 90 92 9e 0e f4 6e
c2 81 46 d1 8d d3 d5 8e cc e4 70 58 15 00 d4 14
c8 8f e4 29 11 fe 30 17 3e 4a 01 2b 5e 48 95 45
f3 9a 61 4a 38 e2 ff fa 6c cc 3b f2 aa 2c d2 c8
d3 83 ff 30 ab df 32 8a db 03 2d ad 03 be 8d 75
dd fc 40 7c 1c ab fb 52 b4 36 b8 38 cc 79 33 10
16 6c bb a0 db 95 dd b1 24 41 3b 0b af 5b a0 ad
5f 19 60 e8 89 f0 75 98 79 1e dd 2f 7d 68 a3 cc
17 9c 76 06 11 e9 a2 f7 f9 a6 5a d3 b7 5d 29 0e
5f 02 96 3a 20 7b b4 37 95 a6 99 11 3d dc 10 d8
cf 86 58 3c 28 1d 20 ca 8c d6 7b a7 30 f6 2e 13
5f 0b d4 b6 49 f5 e7 64 9d dd c7 58 a4 2b 67 6b
63 d5 65 6e 3c 21 7f fa 2b 20 d7 19 90 ce 61 c7
10 86 29 28 37 1a eb 00 db 4d 67 63 ac aa 63 0e
e9 30 b1 74 a0 b8 6e 96 9e dd 18 9d 4d 63 f0 df
ee 0b e9 f9 52 74 cf ab c0 0e 95 6c 22 c5 53 2b
b0 bb 55 39 94 ce 52 e4 30 87 ce 02 f3 3e 61 4f
f5 2b 6a 79 8e b6 99 7f ca 3a c7 fe dc 05 d0 fb
72 ab be 3d 55 b9 6b d7 92 53 10 72 7f 9e 76 78
82 18 fd 8e 15 e2 a7 7d 05 d3 03 8e 8d 27 31 3f
28 07 04 c8 4a 26 61 06 ba 4b 21 aa e3 1b 22 5a
a8 c2 f8 e8 3f 79 2e 28 ae d5 22 d2 ba 16 92 0b
6e 95 b0 84 27 2d b4 a8 77 cc d2 c2 14 50 3b a3
5d f3 07 19 f4 a2 f3 79 0b 46 5a 0c 98 21 45 72
f9 a0 19 07 1c 31 3e 60 07 67 49 80 ae f1 7f e9
d3 61 39 c0 db 05 c9 82 01 8d 78 c5 e6 6c e0 a1
58 c9 10 82 33 fb cc 08 f7 c1 d9 27 de 73 bb e2
f3 c4 5b 35 a1 9b b8 4d e3 13 9a f2 f0 02 3f a5
de 31 83 42
```

### 2018-06-19 PBIN HEADER
```
50 41 4e 01 19 cc b3 58 9a 6b f3 76 3d 14 af 2c
5c ec 11 42 4d 07 5f 03 bf 1a f3 b4 bf 4c 18 bf
cd d7 bd ec c4 61 45 07 96 d8 23 b3 2c 48 20 a2
10 cb dd 50 4a c9 8e 59 b7 f2 a6 74 5d ba 8e b7
f2 fe 4f ae 98 3b fd 4f d9 b7 39 eb a2 0e 01 58
25 9f 72 1e c1 27 8d ef f8 15 97 42 de 50 01 87
79 04 bb e0 46 63 9c 0d 0e a0 26 0f be 74 da 52
e7 fd 42 ff 65 fa c3 54 3c 17 32 0d 71 a4 01 d2
9f d9 da 76 63 b0 2f 76 b4 41 cd fe b9 cf 37 2c
b1 22 13 b6 a1 18 32 3f 7d 95 50 5e 75 9a ed bf
27 b7 78 c9 42 ae 30 22 79 9b 67 c1 ef be 3d c9
38 29 b4 a1 e1 84 fb 4c dc 4e 13 94 37 13 e4 76
35 3d f3 4f 80 60 01 86 c8 2a 37 ef e2 ca b4 aa
db b9 93 87 93 24 74 d9 57 f1 cf 17 09 96 c5 ad
27 a9 2f be 3c bf 11 00 75 1c 3c 4a a0 9d 23 7c
6e 09 7d e9 38 9c d5 dd 1f dd 2a b4 74 61 c1 df
f9 90 46 69 13 aa 92 cb 17 bc 08 18 53 0e 6c 53
57 06 b0 dd 9b fb 60 b3 d4 e1 ac 1a 74 d8 4f 7a
aa c6 e1 ee 8c 83 6a 12 1c be 9e 1e 59 cd ad 2a
89 7a 2d 21 a9 8a 39 1e 6b d7 0e 60 60 2c dd f5
cf 69 59 ea 73 40 01 f7 3b 93 6e e2 ff 76 b8 9d
df 21 a2 c4 6a 20 d2 b3 46 56 83 de b2 5f c5 8f
51 9b 52 f0 f5 74 f0 5e d7 e1 47 fc 23 83 b0 89
28 f4 96 99 c8 24 6e ed 2d 88 73 ea c0 ad 69 40
92 f9 fa c6 db ed 3b 69 a8 5b 5a 3c 48 64 16 57
25 e4 87 2f e8 db 8d ca e5 55 c7 f6 89 ec 91 98
66 64 86 50 e5 0f 3b 1a a7 3a 13 fb 29 19 17 a7
10 c8 88 59 23 fc ca a1 e8 db 52 01 b2 bd f2 22
d7 7f 5d 5e df 65 ff 36 84 ff 97 d7 4f 95 31 e2
db 16 7a 23 0a a2 1a ea 12 6e 4f b6 f2 be 1b 23
0a 38 f5 55 db 77 9d 03 13 27 08 d4 73 ed c9 f5
a9 2b 76 c8 2c 29 7d bd 5a 2a f9 99 fb 44 77 63
80 4e 1f 5a
```

---

# Local file header

It appears to store files using the structure of a PKZip file, as described [here](https://users.cs.jmu.edu/buchhofp/forensics/formats/pkzip.html).  

These are the headers at offset `0x00000204`. They describe the first stored file (`panorama\csgo_keybinds.cfg`).  
As defined in the link above:  
- The signature is always `50 4b 03 04`.
- Version is `0a` for both versions of `csgo_keybinds.cfg`.
- Flags, Compression, Mod time and Mod date fields are 00.
- CRC32 was changed.
- Compressed and Uncompressed size are the same, but differ between versions.
- File name length is `1a` (26 decimal, the length of `panorama\csgo_keybinds.cfg`).
- Extra field length is 00.
- File name is `panorama\csgo_keybinds.cfg` in hex.


### 2018-06-20 local file header
```
50 4b 03 04 0a 00 00 00 00 00 00 00 00 00 82 c2
a9 51 f8 01 00 00 f8 01 00 00 1a 00 00 00 70 61
6e 6f 72 61 6d 61 5c 63 73 67 6f 5f
```

### 2018-06-19 local file header
```
50 4b 03 04 0a 00 00 00 00 00 00 00 00 00 11 25
64 c1 f0 00 00 00 f0 00 00 00 1a 00 00 00 70 61
6e 6f 72 61 6d 61 5c 63 73 67 6f 5f
```
