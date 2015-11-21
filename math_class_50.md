# Math Class (50)

## Problem

Use the programming interface to complete this task. You&#39;ll be given a math expression, such as `add 1 2` or `subtract 5 3`, where you will perform the operations `1+2` and `5-3`, respectively.

ID:&nbsp;`math-class` 

Input: An expression in the form of `operation operand1 operand2`, separated by spaces. Read input from `math-class.in`.

Output: The **absolute** value of the evaluated&nbsp;expression. Your output should always be a positive integer.

There are only 2 different possible operations, addition and subtraction, and all operands will be integer values between 1 and 1000. As always, remember to end your program with a newline.

## Hint

Two very useful functions are `int()` and `split()`. Read about them in the documentation.

## Writeup
```python
file1 = open("math-class.in", 'r')
file2 = open("math-class.out", 'w')
s = file1.read()
a = s.split(" ")
x = 0
if a[0] == "add":
  x = int(a[1]) + int(a[2])
else:
  x = int(a[1]) - int(a[2])
file2.write(str(abs(x))+"\n")
file1.close()
file2.close()

```

## Flag
`easyctf{have_y0u_had_enough_of_math_in_sk0ol_yet}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#math-class---50-points-
