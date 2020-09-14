# Unit 1: Electronic hardware store 

## Criteria A: Planning 

### Context of the problem 
There is a hardware store in Karuizawa. This store is quite old, like 1000 year old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment, is kept on paper. He would like to have a software application that replaces the accounting book. Mr Sakamoto got a new Mac PC from his nephew and would  like to use it.


### Justification of the solution 
We weant to create a text based application that runs on a caomputer, which provides the functionality for the hardware store. The app should provide actions such as record of purchases, categorisation of items, record of inventory, calculations of totals, edit and deleting records, billing. We will develop this application using Python. We will use Python because it is the software we are using in class at the moment. In comparison to C++ or C, Python has a lean and simple programming syntax. In addition, Python has become the most popular programming language over the last years [1]. Similarly, Python has a large repository of libraries and documentation. 

T.E.L.O.S study: 

[1] Eastwood, Brian. “The 10 Most Popular Programming Languages to Learn in 2020.” Northeastern University Graduate Programs, 27 Aug. 2020, www.northeastern.edu/graduate/blog/most-popular-programming-languages/. 

![Diagram](https://github.com/isabelandreatta1/Unit-1/blob/master/SakamotoDiagram.png) 

## Criteria C: Development 
1. Provides clear feedback to the user 
1. **There are no bugs in the application** 
1. The application should allow to calculate the total and billing 
1. Secure application: It allows user login/authentification 

![Diagram](https://github.com/isabelandreatta1/Unit-1/blob/master/Flow%20Diagram.png)

```.py 

from datetime import datetime
import pytz 

IST = pytz.timezone('Asia/Tokyo')
datetime_ist = datetime.now(IST)
date = datetime_ist.strftime("Date: %Y.%m.%d. Time: %H:%M")

print("Welcome to Sakamoto Store {}".format(date))
print ("Hello user. Please enter your name.")
name= input()
print("Your name is " + name)
#Can you create a list of Menu Items 
print("\n Menu of items") 
print("=" * 50)
items_and_price = [("RAM", "3"), ("CPU", "5"),("Motherboard", "5"),("Motherboard","5"),("GPU", "8")]

item_no = 1;  
for item in items_and_price: 
  print("\n" + item[0] + "..." *10 + item[1], " Bitcoin")
  item_no = item_no + 1

print("\n Please input option purchased:")

count = 0 
while count < 3:
    count = count + 1
    option = int(input())
    if option <= 5:
        print("You chose {}".format(option))
        break
    elif count==3:
        print("You have 0 tries left")
    else:
        print("You have {} tries left".format(3 - count))
while True: 
  total = int(input("Please enter the total amoiunt (BTC) "))
  if total < 0: 
    print("The total cannot be negative. Try again")
  else: 
      break

#Step 2: withou using pattern recognition 
for n in range(4): 
  if 250*n < total <= 250*n + 250: 
    tax = 0.25 - (n*1)
  if total > 1000: 
    tax = 0.05 
#step 3: Show the total in a nice frame 
finalprice = total* (tax + 1 )  

for n in range(50):
  print("X",end = "")
print("\nX", " " * 15, "{:3f} BTC".format(finalprice) , " " * 14, "X")
print("X" * 50)


```

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

