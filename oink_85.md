# Oink (85)

## Problem

Use the programming interface to solve this problem.

Pig Latin is a &quot;secret&quot; language in which English words are changed to sound foreign. Its rules are pretty simple:

* If the English word begins with a vowel, add &quot;yay&quot; to the end.
* If the English word begins with a consonant, move the first letter to the end and then add &quot;ay&quot;.

For example, &quot;Apples are Delicious&quot; becomes &quot;Applesyay areyay eliciousDay&quot;. Note: if you know a version of Pig Latin that uses a variation of rules different from the above rules, please use the above rules for this problem.

Your job is to translate English input to Pig Latin output. For this exercise, keep capitalized letters capitalized, even when they are moved.

ID: `piglatin1`

Input: A sentence in English.

Output: The translation in Pig Latin.

Read the input from a file called&nbsp;`piglatin1.in`&nbsp;that&#39;s in the current working directory, and then write your output to a file called&nbsp;`piglatin1.out`.

## Hint

Words are defined as separated by spaces. :)

## Writeup
```python
file1 = open("piglatin1.in", 'r')
s = file1.read().strip()
words = s.split(" ")
vowels = ["a", "e", "i", "o", "u", "A", "E", "I", "O", "U"]
final = list()
for x in range(len(words)):
  if words[x][:1] in vowels:
    final.append(words[x] + "yay")
  else:
    final.append(words[x][1:] + words[x][:1] + "ay")
    
file2 = open("piglatin1.out", 'w')
file2.write(" ".join(final) + "\n")
file1.close()
file2.close()

```

## Flag
`easyctf{atinl4y_easyyay_3noughyay_orfay_ayay_1gpay!}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#oink---85-points-
