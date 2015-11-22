# An apple a day keeps the dinosaur away? (35)

## Problem

Oh look, it's a perfectly innocent picture of an [apple](files/apple.jpg). Nothing to see here!

## Hint

Apples are suspicious. Don't trust apples. They always have something to hide . . .

## Writeup

We can use the `strings` command to see the image data.

In the terminal, we type

`$ strings apple.jpg`

Unfortunately, this just returns a lot of gibberish.

What if we look for instances of easyctf{} (the flag format)?

`$ strings -a -t x apple.jpg | grep 'easyctf{.*}'`

This returns the line

```
4b924b    the flag is easyctf{w0w_much_appl3s}
```

Alternatively, you could have just opened up the file in a text or hex editor, and used ctrl-f. But wheres the fun in that?

## Flag

`easyctf{w0w_much_appl3s}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/forensics.md
* https://github.com/ztaylor54/CTF/blob/master/EasyCTF%202015/an_apple_a_day.md
