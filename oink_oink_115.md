# Oink Oink (115)

## Problem

Use the programming interface to solve this problem.

Now that we know how to convert from English to&nbsp;Pig Latin, can we reverse the translation? Given a sentence in Pig Latin, reverse it and try to find the original English text.

Be careful to note that if a Pig Latin word is capitalized, like &quot;Arispay&quot;, the original English word is &quot;Paris&quot; rather than &quot;pAris&quot;. Case counts!

ID: `piglatin2`

Input: A sentence in Pig Latin.

Output: The translation in English.

Read the input from a file called&nbsp;`piglatin2.in`&nbsp;that&#39;s in the current working directory, and then write your output to a file called&nbsp;`piglatin2.out`.

## Hint

Work backwards! You'll probably need the `chr()` and `ord()` functions! Also, string splicing is pretty cool in Python ;)

## Writeup
```python
file1 = open("piglatin2.in", 'r')
s = file1.read().strip()
words = s.split(" ")
final = list()
for x in range(len(words)):
  if words[x][-3:] == "yay":
    final.append(words[x][:-3])
  elif words[x][-3:-2] != "y":
    if ord(words[x][:1]) >= 65 and ord(words[x][:1]) <= 90: #between A-Z
      final.append(chr(ord(words[x][-3:-2]) - 32) + chr(ord(words[x][:1]) + 32) + words[x][1:-3]) 
    else:
      final.append(words[x][-3:-2] + words[x][:-3])
result = " ".join(final)
file2 = open("piglatin2.out", 'w')
file2.write(result + "\n")
file1.close()
file2.close()

```

## Flag
`easyctf{th0se_pesky_capit4ls_were_a_pa1n,_weren't_they?}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#oink-oink---115-points
