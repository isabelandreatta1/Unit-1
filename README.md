# Task 2: Computer Organisation 

### Count to N 
Given an int N, print all numbers from 1 to N 

```.py 
a = int(input("Please choose the number"))
print("You have chosen {}".format(a))
x = 0;
for x in range(a):
    x = x + 1 
    print(x)
```
### Series -1 
Given two intergers A and B (A<= B). Print all numbers from A to B inclusively. 
```.py
a = int(input("Please choose a number"))
b = int(input("Please choose a second number. It must be either equal to or larger than the previous one"))
if b >= a:
    for a in range(a,b+1): #range(start,stop[,step]) 
        print(a)
else:
    print("Number did not fit conditions")
``` 
### Slices 
```.py
S = input()
#print the third chatacter 
print( S[2])
#print the second to last character 
print(S[-2])
#print the first five characters 
print(S[0] + S[1] + S[2] + S[3] + S[4]) 
#print all but the two last characters in this string 
print(S[0:-2]) 
#print all characters with even indexes
print(S[::2]) 
#print all characters with odd indexes 
print(S[1::2]) 
#print all characters in reverseee 
print(S[::-1]) 
#print every second character reverse order 
print(S[-1::-2]) 
#print length of string 
print("{}".format(len(S)))
```
(helpeful link about slicing string: https://www.digitalocean.com/community/tutorials/how-to-index-and-slice-strings-in-python-3 ) 

###  10 numbers ordered from smallest to largest 

```.py
numberList = (input("Please input 10 numbers seperated by a space \n"))
print("\n")
newNumberList = sorted(numberList.split()) 
print("Your list ordered from smallest to largest: \n {}".format( newNumberList)) 
```
**certain problems because of "sorted" ** 
