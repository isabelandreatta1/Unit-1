# Unit 1: Electronic hardware store 

## Criteria A: Planning 

### Context of the problem 
There is a hardware store in Karuizawa. This store is quite old, like 1000 year old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment, is kept on paper. He would like to have a software application that replaces the accounting book. Mr Sakamoto got a new Mac PC from his nephew and would  like to use it.


### Justification of the solution 
We weant to create a text based application that runs on a caomputer, which provides the functionality for the hardware store. The app should provide actions such as record of purchases, categorisation of items, record of inventory, calculations of totals, edit and deleting records, billing. We will develop this application using Python. We will use Python because it is the software we are using in class at the moment. In comparison to C++ or C, Python has a lean and simple programming syntax. In addition, Python has become the most popular programming language over the last years [1]. Similarly, Python has a large repository of libraries and documentation. 

T.E.L.O.S study: 

[1] Eastwood, Brian. “The 10 Most Popular Programming Languages to Learn in 2020.” Northeastern University Graduate Programs, 27 Aug. 2020, www.northeastern.edu/graduate/blog/most-popular-programming-languages/. 

## Criteria for Success
1. Provides clear feedback to the user 
1. **There are no bugs in the application** 
1. The application should allow to calculate the total and billing 
1. Secure application: It allows user login/authentification 

## Criteria B: Design

![Diagram](https://github.com/isabelandreatta1/Unit-1/blob/master/SakamotoDiagram.png) 

*Fig. 1 System Diagram* 

## Record of Tasks 

| Task No | Planned Action                                                                                         | Planned Outcome                  | Time Estimated | Target Completion Date | Criterion |
|---------|--------------------------------------------------------------------------------------------------------|----------------------------------|----------------|------------------------|-----------|
| 1       | Planning: Discuss the context of the situation (Ideally, this is the first interview with your client) | Write the context of the problem | 15m            | Sept 11                | A         |
| 2       | Development: Coded a text-based menu system for some parts in the hardware store                       | A working program                | 80m            | Sept 18th              | C         |
| 3       | Planning: Created a flow-diagram for the menu system                                                   | An easy-to-follow flow diagram   | 20m            | Sept 15th                 | A         |


## Criteria C: Development 

![Diagram](https://github.com/isabelandreatta1/Unit-1/blob/master/Menu%20Flow%20Diagram.png)

*Fig. 2 Menu Flow Diagram* 


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
    tax = 0.25 - (n* 0.05)
  if total > 1000:
    tax = 0.05
#step 3: Show the total in a nice frame
finalprice = round(total* (tax + 1 ))

for n in range(5):
    if n == 0 or n == 4:
        print("X" * 50)
    elif  n == 1 or n == 3:
        print("X", " " * 45, "X")
    elif n == 2:
        print("X", " " * 15, "{} BTC".format(finalprice), " " * 12, "X")

```

## Criteria D: Functionality 
This is a video 

## Criteria E: Evaluation 

