# An apple a day keeps the dinosaur away? (35)

## Problem

Oh look, it's a perfectly innocent picture of an [apple](files/apple.jpg). Nothing to see here!

## Hint

Apples are suspicious. Don't trust apples. They always have something to hide . . .

## External Writeups

When in doubt, use the shell. A quick look at the picture in Terminal with the command:

$ strings apple.jpg

will reveal the hidden message within! Alternatively, open the image in a Hex editor (like Hex Fiend)
and look through the hex-to-string translations, where there might be a hidden message.

Basic steganography involves hiding messages or files within other files (most notably images) by editing the hex values of the file. Online, there are many resources for viewing file signatures (the starting and ending patterns of hex characters that tell the computer what file type it is), like this: http://www.garykessler.net/library/file_sigs.html

By examining the hex values of a .jpg with a hidden file, for example, one might be able to see that there are additional hex values at the end representing this message or file.
