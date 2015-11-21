# Can You Even??? (40)

## Problem

Use the programming interface to complete this task. You&#39;ll be given a list of numbers.

Input: A list of numbers, separated by commas.

Output: The number of even numbers.

Read the input from a file called&nbsp;`can-you-even.in`&nbsp;that&#39;s in the current working directory, and then write your output to a file called&nbsp;`can-you-even.out`.

## Hint

If you need help, try looking at the Python Tutorial in the Learn section! Perhaps you should try looking into the modulo (%) operator. 

## Writeup
```python
file1 = open("can-you-even.in", 'r')
file2 = open("can-you-even.out", 'w')
s = file1.read()
a = s.split(",")
ctr = 0
for x in a:
  if int(x) % 2 == 0:
    ctr += 1
file2.write(str(ctr)+"\n")
file1.close()
file2.close()

```

## Flag
`easyctf{?v=8ruJBKFrRCk}`

## External Writeups

* https://github.com/jbmonsterbananas/easyctf-2015-writeups/blob/master/can_you_even_40.md
* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#can-you-even-40-points-
