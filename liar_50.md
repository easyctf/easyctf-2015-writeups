# Liar (50)

## Problem

I may or may not have illegally bought this [file](files/secret) from someone who claims that it contains secret pictures of my friend and her fiancé. Unfortunately, I can't open it, and I already paid $4096 for it. Can you help me find out if the seller was lying?

## Hint

I feel like something is missing ...

## Writeup

Using hexdump (or opening up the file in a hex editor), we notice suspicious instances of PK, which is common to zip files.

`$ hexdump -C secret`

```
00000000  50 4b 03 04 14 00 08 00  08 00 77 94 63 47 00 00  |PK........w.cG..|
00000010  00 00 00 00 00 00 00 00  00 00 0a 00 10 00 73 65  |..............se|
00000020  63 72 65 74 2e 70 6e 67  55 58 0c 00 05 6f 39 56  |cret.pngUX...o9V|
00000030  01 6f 39 56 f5 01 14 00  ec dd 07 7c 14 65 fa 07  |.o9V.......|.e..|
00000040  f0 f7 7d 67 03 a8 40 16  54 54 54 52 6c d8 20 09  |..}g..@.TTTRl. .|
00000050  28 88 42 12 40 29 16 12  44 a5 69 12 50 14 1b 09  |(.B.@)..D.i.P...|
```

Unzipping the file, we get a new file with a `.png` extension. Unfortunately, the file seems broken. Opening it up in hexdump again, we notice `IHDR` at the beginning of the file and `IEND` at the end, indicating that it is indeed a PNG file.

`$ hexdump -C secret.png`

```
00000000  0d 0a 1a 0a 00 00 00 0d  49 48 44 52 00 00 0a 47  |........IHDR...G|
00000010  00 00 0a f0 08 02 00 00  00 9b c2 e9 4f 00 00 00  |............O...|
```

```
0151db00  00 00 00 00 00 00 00 00  00 e6 d4 19 6c 7d a9 04  |............l}..|
0151db10  3b 00 00 00 00 49 45 4e  44 ae 42 60 82           |;....IEND.B`.|
```

However, a quick look at the [wikipedia](https://en.wikipedia.org/wiki/Portable_Network_Graphics) page tells us that the file is lacking important information in the header, namely the first 4 bytes of the file signature.

In a hex editor, we prepend the bits `89 50 4e 47`, and reopen the image. This gives us the flag.

![](screenshots/liar.png)

## Flag
`easyctf{troll3d}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/forensics.md
* https://github.com/jdeans289/CTF/blob/master/Problems/liar.md
