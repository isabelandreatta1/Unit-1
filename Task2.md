## Task 2: Computer Organisation 

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
## Dice simulation 
```.py
#Simulation for a Fair Dice
#1- Generate a random number 0 to 59
#2 - Check the number; if between [0 9] count as 0
# if between [10 19] count as 1
import random 
import matplotlib.pyplot as plt
count = [0,0,0,0,0,0]
num_trial = int(input("Please write the number of trials: "))

for trial in range(num_trial): 
  n = random.randint(1,60)
  if n < 9: 
    count[0] += 1
  elif 9 < n < 19: 
    count[1] += 1
  elif 19 < n < 29: 
    count[2] += 1
  elif 29 < n < 39: 
    count[3] += 1
  elif 39 < n < 49 :
    count[4] += 1 
  elif 49 < n < 59: 
    count[5] += 1

for index, c in enumerate(count): 
  error =  c - num_trial/6
  print("Number of {}s: {}, expected {}, error {}".format(index + 1, c, num_trial/6, error))
  
MSE1 = (1/num_trial) * (error)**2
print(MSE1)

x = [10000,20000,30000,40000,50000,60000,70000,80000,90000,100000]
y = [1.746, 2.413, 3.343, 3.83,4.433,4.474 ,4.284 , 5.089, 5.347, 5.324]

plt.plot(x,y) 
plt.xlabel("Number of trials")
plt.ylabel("Average Squared Error")
plt.show()

```

## Architecture of the computer 

![Diagram](https://github.com/isabelandreatta1/Unit-1/blob/master/Computer%20Architecture.jpg)

*Fig. 3 Computer Architecture by Cathy, Timur, Isabel and Kien* 

This is a diagram of a computer designed by our team. Though it includes many computer conponments, there is little coherance because some parts are more uneccessarily complex while others are very simple. For the input/output interfaces of the computer, the computer contains USB port, a HDMI port (for the integrated video), a soundcard, and mouse/keyboard port. The videocard inside the motherboard, 
