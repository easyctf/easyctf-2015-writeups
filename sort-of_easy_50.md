# Sort-of Easy (50)

## Problem

Use the programming interface to complete this task.

Input: A list of numbers, separated by commas. Ex: `3,28,9,17,5`

Output: The list sorted from largest to smallest, separated by commas. Ex: `28,17,9,5,3`

Read the input from a file called&nbsp;`sorting-job.in`&nbsp;that&#39;s in the current working directory, and then write your output to a file called&nbsp;`sorting-job.out`.

## Hint

I wonder if there is a handy sort function for this? 

## Writeup
```python
file1 = open("sorting-job.in", 'r')
s = file1.read().strip()
a = s.split(",")
numList = list()
for x in a:
  numList.append(int(x))
b = sorted(numList, reverse=True)
c = ",".join([str(j) for j in b])
file2 = open("sorting-job.out", 'w')
file2.write(c + "\n")
file1.close()
file2.close()
```

## Flag
`easyctf{sorting_is_as_easy_as_3_2_1!}`

## External Writeups

* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#sort-of-easy---50-points-
