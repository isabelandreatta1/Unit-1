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

