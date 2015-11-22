# Misaka Mikoto (50)

## Problem

My friends like anime way too much . . . they decided that to give me an encoded [message](files/message.txt), but I can't solve it because I'm not a weeb!

## Hint

railguns are cool

## Writeup

Since this is a crypto challenge, we first do a quick google search of "railgun cipher"

One of the results mentions something called a "rail fence cipher"

Using [rumkin](http://rumkin.com/tools/cipher/railfence.php), we can try different rails on the ciphertext.

A rail of 5 gives us `railgunsarethebesteasyctfl3v3l5esp3rs`

If you didn't want to go click through the rails, googling "misaka mikoto" yields a wikia page, which tells us

> She is the third ranked Level 5 esper in Academy City, and is nicknamed the Railgun due to her signature move.

Using this clue we can guess that the rail value is 5

## Flag

`easyctf{l3v3l5esp3rs}`

## External Writeups

* https://www.gitbook.com/book/johnwig/misaka-mikoto/details
* https://github.com/jbmonsterbananas/easyctf-2015-writeups/blob/master/misaka_mikoto_50.md
* [A Certain PHS Absol's Writeup](https://github.com/MegaAbsol/EasyCTF-2015-Writeups/blob/master/Misaka%20Mikoto%20-%2050.md)
