# Unit 1: Electronic hardware store 

## Criteria A: Planning 

### Context of the problem 
There is a hardware store in Karuizawa. This store is quite old, like 1000 year old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment, is kept on paper. He would like to have a software application that replaces the accounting book. Mr Sakamoto got a new Mac PC from his nephew and would  like to use it. 

### Justification of the solution 
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

```
### Dice simulation 
```.py
# Simulation for a Fair Dice
# 1- Generate a random number 0 to 59
# 2 - Check the number; if between [0 9] count as 0
# if between [10 19] count as 1

import random

count = [0, 0, 0, 0, 0, 0]
num_trial = 2000

for trial in range(num_trial):
    n = random.randint(1, 60)
    if n < 9:
        count[0] += 1
    elif 9 < n < 19:
        count[1] += 1
    elif 19 < n < 29:
        count[2] += 1
    elif 29 < n < 39:
        count[3] += 1
    elif 39 < n < 49:
        count[4] += 1
    elif 49 < n < 59:
        count[5] += 1

for index, c in enumerate(count):
    error = c - num_trial / 6
    print("Number of {}s: {}, expected {}, error {}".format(index + 1, c, num_trial / 6, error))
MSE = (1 / num_trial) * (error) ** 2
print(MSE)
```

