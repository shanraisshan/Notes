# [100 Days Python Code Challenge](https://www.youtube.com/playlist?list=PLu0W_9lII9agwh1XjRt242xIpHhPT2llg)
backup [Github Repo](https://github.com/CodeWithHarry/100-days-of-code-youtube/tree/main) of 100 episodes


#### Run a project
```python
Go to your project folder using Finer -> Right Click -> New Terminal at folder
source venv/bin/activate
uvicorn main:app --reload

pip install -r requirements.txt
```

#### Basics (function, condition, loop)
```python
# https://peps.python.org/pep-0008/
def my_function_name(items: str): #don't need return type
    for i in items:
        if i!='a': #if(i!='n'): wrong syntax
            print(i)
    return 5        

items = "Shayan"
x = my_function_name(items) #define function before calling it
```

### [Day1](https://replit.com/@shanraisshan/Day1Python#main.py)

```python
print("hello world")
```

### Day2

```python
print(value := 10) #walrus operator
```

### Day3

```python
# pep3 install pandas #pip3 for mac termincal```
# import pandas
```

### Day4

```python
println(17*13)
```

### Day5

```python
# This is a comment

# for multi line comment use triple ''' or """

# Alt + ↓ #to move line

# Escape Sequence Characters \n \"
print("I am a good \"boy\" and\nthis is new line")

print("Hey", 6, 7, sep="~", end="009\n")
```

### Day6

```python
a=1
b=True
c="Harry"
d=None
print("the type of a is:", type(a))
print("the type of a is:", type(b))


# Sequenced Data: list, tuple
list1 = [8, 2.3, [-4,5], ["apple","banana"]] #changeable
print(list1)
tuple1 = (("parrot","sparrow"), ("lion, tiger")) #unchangeable
print(tuple1)

# Mapped Data: dict
dict1 = {"name":"Shayan", "age":20, "is_engineer":True} #key-value pairs
print(dict1) 

# everything in python is object
```

### Day7

```python
print(5+2) #7
print(5-2) #3
print(5*3) #15
print(2**4) #2^4=16
print(5/2) #2.5
print(5//2) #2
```

### Day8

```python
# Alt + Shift + ↓ #copy line
# Alt + Click #multiple cursors
```

### Day9 - type conversion

```python
#explicit type conversion
a = "1"
b = "2"
print(int(a) + int(b)) 

#implicit type conversion
c = 1 # int will be converted into float 1.0
# python convert lower data type to higher data type to prevent data loss
d = 2.1
e = c + d
print(e) 
print(type(e)) #<class 'float'>
```

### Day10 - input()

```python
a = input("Enter first number:")
b = input("Enter second number:")
print("The sum of two numbers is:", int(a) + int(b))
```

### Day11 - Strings
```python
name = "Shan"
print(name[0] + "= index:" + str(name.index('S'))) #S at index: 0
items = "Mango"
for i in items:
    print(i)
```

### Day12 - Strings Slicing
```python
fruit = "Mango"
print(len(fruit)) #5
print(fruit[0:4]) #Mang
print(fruit[:4]) #Mang
print(fruit[1:]) #ango
print(fruit[:]) #Mango
print(fruit[-1]) #same as fruit[4] #o => len(fruit)-1: 5-1=4
print(fruit[-4:-2]) #fruit[1:3] #an
```

### Day13 - Strings Method
```python
a = '!Harrry!!!' #string are immutable
print(a.upper()) #HARRY!!!
print(a) #!Harrry!!!
print(a.rstrip('!')) #!Harrry
b = 'a b c'
print(b.split( )) #['a', 'b', 'c']
```

📷 19:58 record with OBS + continuity camera

### Day14 - If Else Conditional Statement
```python
age = int(input('Enter your age: '))
if age>18: #if(age>18): wrong syntax
    print("You can drive")
else:    
    print("You can't drive")
```

### Day15 - If Else Time
```python
import time
from time import gmtime, strftime
current_time = time.time()
print(strftime("%a, %d %b %Y %H:%M:%S", gmtime(current_time)))
if int(time.strftime("%H"))>12:
    print("Good Afternoon")
```

### Day16 - Match Case Statment (added in Python3.11)
```python
# there is no break statement in case block like C, C++, Java
x = 52
match x:
    case 0:
        print("x1 is 0")
    case 100:
        print("x2 is 100")
    case _ if x<50: #you can add if in default case
        print("x3 is less than 50")
    case _ if x>50:
        print("x4 is greater than 50")
    case _:
        print("x5 is 50")
```

### Day17 - For Loops
```python
name = "Abc"
for i in name:
    print(i)
for i in range(3):
    print('.',i)
```

### Day18 - While Loops
```python
n = 0
while n < 3:
    print('..',n)
    n += 1
else:
    print('else block')
```

### Day19 - While Loops
```python
for i in range(10):
    if i==2:
        continue
    elif i==5:
        break
    else:
        print(i)
```

### Day20 - Functions
```python
def my_function_name(items: str):
    pass
```

### Day21 - Function Arguments
```python
def sum(a,b): #positional argument
    return a+b
print(sum(1,5)) #6

def sum(a=2,b=5): #default argument
    return a+b
print(sum()) #7

def sum(a,b): #keyword argument
    return a+b
print(sum(b=5,a=3)) #6

def sum(*numbers): #arbitrary argument
    print(type(numbers))#<class 'tuple'>
    result = 0
    for i in numbers:
        result=result+i
    return result
print("sum is:",sum(4,5)) #sum is: 9

def name(**names): #keyword arbitrary argument
    print(type(names))#<class 'dict'>
    for key, value in names.items():
        print(key, value)
print(name(first='Shayan', last='Rais'))
```

### Day22 - Lists
```python
list = [1, "two", True]
print(list) #[1, 'two', True]
if 1 in list:
    print("Yes, 1 is in list") #Yes, 1 is in list
lst = [i for i in range(5) if i>2]
print(lst) #[3, 4]
```

### Day23 - List Functions
```python
one = [4, 3, 2, 1]
two = one
two[0] = 5
print(one) #[5, 3, 2, 1] org one list changed
one.insert(0, 100)
print(one) #[100, 5, 3, 2, 1]
```

### Day24 - 11/Jan/25 - Tuples
```python
tup = (1, 2, 2, "ABC")
# tup[2] = 100 #TypeError: 'tuple' object does not support item assignment
print(tup[3]) #ABC
```

### Day25 - 12/Jan/25 - Operations on tuples
```python
tup.index(2) #1
```

### Day26 - 13/Jan/25
```python
exercise
```

### Day27 - 14/Jan/25
```python
kbc program
```

### Day28 - 15/Jan/25 - fStrings
```python
name = "Shayan"
print(f"my name is {name}") #my name is Shayan
```

### Day29 - 16/Jan/25 - Docstrings PEP8
```python
def square(x):
    '''this is docstring'''
    return x * x
print(square.__doc__) #this is docstring

#Python Enhancement Proposal (PEP8)
import this
The Zen of Python, by Tim Peters (poem)
```

### Day30 - 17/Jan/25 - Recurssion
```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)
print(factorial(5)) #120
```

### Day31 - 18/Jan/25
```python
```

### Day32 - 19/Jan/25
```python
```

### Day33 - 20/Jan/25
```python
```

### Day34 - 21/Jan/25
```python
```

### Day35 - 22/Jan/25
```python
```

### Day36 - 23/Jan/25
```python
```

### Day37 - 24/Jan/25
```python
```

### Day38 - 25/Jan/25
```python
```

### Day39 - 26/Jan/25
```python
```

### Day40 - 27/Jan/25
```python
```

### Day41 - 28/Jan/25
```python
```

### Day42 - 29/Jan/25
```python
```

### Day43 - 30/Jan/25
```python
```

### Day44 - 30/Jan/25
```python
```

### Day45 - 31/Jan/25
```python
```

### Day46 - 1/Feb/25
```python
```

### Day47 - 2/Feb/25
```python
```

### Day48 - 3/Feb/25
```python
```

### Day49 - 4/Feb/25
```python
```

### Day50 - 5/Feb/25
```python
```

### Day51 - 6/Feb/25
```python
```

### Day52 - 7/Feb/25
```python
```

### Day53 - 8/Feb/25
```python
```

### Day54 - 9/Feb/25
```python
```

### Day55 - 10/Feb/25
```python
```

### Day56 - 11/Feb/25
```python
```

### Day57 - 12/Feb/25
```python
```

### Day58 - 13/Feb/25
```python
```

### Day59 - 14/Feb/25
```python
```

### Day60 - 15/Feb/25
```python
```

### Day61 - 16/Feb/25
```python
```

### Day62 - 17/Feb/25
```python
```

### Day63 - 18/Feb/25
```python
```

### Day64 - 19/Feb/25
```python
```

### Day65 - 20/Feb/25
```python
```

### Day66 - 21/Feb/25
```python
```

### Day67 - 22/Feb/25
```python
```

### Day68 - 23/Feb/25
```python
```







