# Looking for Letters (65)

## Problem

Use the programming interface to complete this task.

Input: A string containing alphanumeric characters.

Output: A string containing only the letters of the input.

Read the input from a file called&nbsp;`looking-for-letters.in`&nbsp;that&#39;s in the current working directory, and then write your output to a file called&nbsp;`looking-for-letters.out`.

## Hint

If you need help, try looking at the Python Tutorial in the Learn section!

## Writeup
```python
file1 = open("looking-for-letters.in", 'r')
s = file1.read().strip()
characters = [c for c in str(s)]
final = list()
for x in characters:
  if ord(x) >= 65 and ord(x) <= 90:
    final.append(x)
  elif ord(x) >= 97 and ord(x) <= 122:
    final.append(x)
letters = "".join(final)
file2 = open("looking-for-letters.out", 'w')
file2.write(str(letters) + "\n")
file1.close()
file2.close()
```

## Flag
`easyctf{filtering_the_#s_out}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#looking-for-letters---65-points
