# Unit 1: Electronic hardware store 

## Criteria A: Planning 

### Context of the problem 
There is a hardware store in Karuizawa. This store is quite old, like 1000 year old. The owner, Mr Sakamoto, wants to upgrade his accounting software, which at the moment, is kept on paper. He would like to have a software application that replaces the accounting book. Mr Sakamoto got a new Mac PC from his nephew and would  like to use it. 

### Justification of the solution 

```.py 
from datetime import datetime

date = datetime.today() 
print("Welcome to Sakamoto Store {}".format(date))
print ("Hello user. Please enter your name.")
name= input()
print("your name is " + name)
#Can you create a list of Menu Items 
print("Menu of items") 
print("=" * 20)
print("1.{}{}".format("Ram","3$")) 
print("2.{}{}".format("CPU","5$")) 
print("3.{}{}".format("Motherboard","5$")) 
print("4.{}{}".format("GPU","8$"))
print("Please input option purchased:")
option = int(input())
if option == 1:
  print("You have chosen RAM")
elif option == 2: 
  print("You have chosen CPU")
elif option == 3:
  print("You hav chosen Motherboard")
elif option == 4:
  print("You have chosen GPU")
else:
  print("Please input a listed number")
  
  #loop the input listed number 
  

```

