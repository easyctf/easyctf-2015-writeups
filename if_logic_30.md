# If Logic (30)

## Problem

Use the programming interface to complete this task. You&#39;ll be given a list of numbers.

Input: A list of numbers, separated by commas.

Output: Print `hi`if the number is 0-50 (inclusive), `hey` if the number is 51-100 (inclusive), and `hello` if anything else. Each greeting should have a linebreak after it.

Read the input from a file called&nbsp;`if-logic.in`&nbsp;that&#39;s in the current working directory, and then write your output to a file called&nbsp;`if-logic.out`.

## Hint

If you need help, try looking at the Python Tutorial in the Learn section!

## Writeup
```python
file1 = open("if-logic.in", 'r')
s = file1.read().strip()
a = s.split(",")
text = ""
for x in a:
  if int(x) >= 0 and int(x) <= 50:
    text += "hi\n"
  elif int(x) > 50 and int(x) <= 100:
    text += "hey\n"
  else:
    text += "hello\n"
file2 = open("if-logic.out", 'w')
file2.write(text)
file1.close()
file2.close()

```

##Flag
`easyctf{is_it_hi_or_hey_or_something_else}`

## External Writeups

* https://github.com/ztaylor54/CTF/blob/master/EasyCTF%202015/if_logic.md
* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#if-logic---30-points-
