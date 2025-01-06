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







