# Yve's Fave Pic (275)

## Problem

@chaosagent doesn't like people seeing pictures of his face. So naturally, here's a [picture](files/smile.jpg) of his face. Have fun :)

## Hint

Note: This is a VERY rare occurrence. @chaosagent NEVER smiles. Make note of it. Oh, wait, you wanted a hint? Fine. You need some programming to solve this efficiently.

##Writeup
After downloading the image, the first thing we should do is open it in `hexdump` or a hex editor.

`$ hexdump -C smile.jpg`

```
0007b620  00 00 40 fd 41 e8 0d 00  00 5f 5f 4d 41 43 4f 53  |..@.A....__MACOS|
0007b630  58 2f 7a 69 70 70 69 64  79 2d 64 6f 6f 2f 55 58  |X/zippidy-doo/UX|
0007b640  08 00 ff 1e 06 56 ff 1e  06 56 50 4b 01 02 15 03  |.....V...VPK....|
0007b650  14 00 08 00 08 00 06 ab  39 47 5c 30 0f 34 32 00  |........9G\0.42.|
0007b660  00 00 78 00 00 00 1f 00  0c 00 00 00 00 00 00 00  |..x.............|
0007b670  00 40 a4 81 2b 0e 00 00  5f 5f 4d 41 43 4f 53 58  |.@..+...__MACOSX|
0007b680  2f 7a 69 70 70 69 64 79  2d 64 6f 6f 2f 2e 5f 74  |/zippidy-doo/._t|
0007b690  65 78 74 2e 74 78 74 55  58 08 00 fd 1e 06 56 eb  |ext.txtUX.....V.|
0007b6a0  1d 06 56 50 4b 05 06 00  00 00 00 05 00 05 00 7f  |..VPK...........|
0007b6b0  01 00 00 ba 0e 00 00 00  00 ff d9                 |...........|
0007b6bb
```

It seems that the file DOES end with the JPEG file trailing bits `FF D9`, but we also see suspicious instances of "zippidy-doo". Let's see if there are any other instances of `FF D9`

Modifying our command to grep for `ff d9`, we see that there are actually TWO instances of it. So the file was trying to mislead us!

`$ hexdump -C smile.jpg | grep 'ff d9'`

```
0007a660  46 94 39 c7 5a f3 a8 eb  ff d9 50 4b 03 04 0a 00  |F.9.Z.....PK....|
0007b6b0  01 00 00 ba 0e 00 00 00  00 ff d9                 |...........|
```

In addition, we see the instances of PK right after the JPG file trailer and at the end of the original image, suggesting a zip file. We copy all of the data after the first `ff d9` into a new file, and unzip it. This gives us a folder called zippidy-doo, with a file called [text.txt](files/text.txt) inside.

Opening the file, we see that it consists of a lot of nonsense.

Ignoring the brackets and backslashes at the beginning, we instead analyze the text starting from `METIHBITrloneunh.i   t e zutw t`. What's interesting is that the file consists entirely of letters and punctuation. Moreover, the first eight characters are all capitalized, but this doesn't happen again anywhere else in the file. This, coupled with the unusual spacing between the letters, suggests that perhaps the message is a bunch of texts mashed together one letter at a time (8 texts to be precise, as the first 8 letters are capitalized).

We write a short python script to test this theory.

```python
f = open('text.txt').read().strip()
message = ''
for c in range(0,len(f)):
        if c % 8 == 0:
                message += f[c]
print message
```

This returns the text

> Mr. Jefferson, though too revolutionary in his notions, is yet a lover of liberty and will be desirous of something like orderly Government ??? Mr. Burr loves nothing but himself ??? thinks of nothing but his own aggrandizement ??? and will be content with nothing short of permanent power in his own hands ??? No compact, that he should make with any passion in his  breast except Ambition, could be relied upon by himself ??? How then should we be able to rely upon any agreement with him?  Mr. Jefferson, I suspect will not dare much Mr. Burr will, dare every thing in the sanguine hope of effecting every thing. Alexander Hamilton}

Our theory was correct, but unfortunately this text does not have the flag. What if we viewed the other 7 texts?

Modifying our code, and writing the output to a new file called [smile.txt](files/smile.txt), we get the 8 compiled texts (which are excerpts of various 18th and 19th century essays and books plus MLK's I Have a Dream speech). The flag is in the text of the King speech.

```python
s = open('text.txt').read().strip()
def get_message(n):
        message = ''.join([s[i] for i in xrange(n, len(s), 8)])
        return message
fout = open('smile.txt','w')
for i in range(8):
        fout.write(get_message(i) + '\n\n')
fout.close()
```

##Flag
`easyctf{yeymastery}`

## External Writeups

*None yet!*