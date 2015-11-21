# String Change (70)

## Problem

Use the programming interface to complete this task. Given an array of 5 numbers, change every nth character, with n being the value of the first number of the array and the first letter of the string as the 1st character, of a string and move its value up by one (a turns into b, z turns into a). Repeat this for the rest of the numbers of the array and return the changed string. Do this for all the strings. Be careful to keep the original capitalization!

For example: `[2,3,7,5,4]` and `oTerNmIWxGqaaV` would become `oUftOoJYyIqdaX`.

ID: `string-change`

Input: Read the input from a file called `string-change.in` that contains a string of: a list of 5 numbers separated by commas followed by a linebreak, and then a string of random characters.

Output: The string changed according to the values in the list, written to a file called `string-change.out`.

You already know this, but don&#39;t forget to end your output with a newline.

## Hint

First, look into string splitting, and the <code>ord()</code> and <code>chr()</code> functions!

## Writeup
```python
file1 = open("string-change.in", 'r')
s = file1.read().split("\n")
numList = list()
for x in s[0].split(","):
  numList.append(str(x))
randString = s[1]

def strChanger(s,a): #s=string, a=array of numbers
  charList = list(s)
  for x in a:
    for i in range(len(s)):
      if i < len(s) and (i+1)%int(x) == 0:
        if ord(charList[i]) < 122 and ord(charList[i]) >= 97: #a-z
          charList[i] = chr(ord(charList[i])+1)
        elif ord(charList[i]) == 122:
          charList[i] = chr(97)
        elif ord(charList[i]) < 90 and ord(charList[i]) >= 65: #A-Z
          charList[i] = chr(ord(charList[i])+1)
        elif ord(charList[i]) == 90:
          charList[i] = chr(65)
  newStr = "".join(charList)
  return newStr

result = strChanger(randString,numList)

file2 = open("string-change.out", 'w')
file2.write(str(result) + "\n")
file1.close()
file2.close()
```

## Flag
`easyctf{changing_things_up_once_in_a_while_is_gooood_for_you}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#string-change---70-points-
