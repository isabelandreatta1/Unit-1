#Task 2: Computer Organisation 

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
