#Sum It! (30)  
##Problem  
Use the programming interface to complete this task. You'll be given a list of numbers.  
  
Input: A list of numbers, separated by commas.  
Output: The sum of the numbers.  
  
Read the input from a file called `addition.in` that's in the current working directory, and then write your output to a file called `addition.out`.  
  
##Hint
If you need help, try looking at the Python Tutorial in the Learn section!  
  
##Writeup
```python
file1 = open("addition.in", 'r')
file2 = open("addition.out", 'w')
s = file1.read()
a = s.split(",")
summed = 0
for x in a:
  summed += int(x)
file2.write(str(summed)+"\n")
file1.close()
file2.close()

```

  
##Flag
`easyctf{'twas_sum_EZ_programming,_am_I_rite?}`
  
## External Writeups  
* https://github.com/ztaylor54/CTF/blob/master/EasyCTF%202015/sum_it.md
* https://github.com/1lastBr3ath/EasyCTF-2015-Writeup/blob/master/programming.md#sum-it---30-points
