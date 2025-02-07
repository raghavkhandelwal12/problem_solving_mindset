# **Task 8 : For loops**

**For Loops** : Iterates over sequences like `list, tuples, strings, ranges, and dicitionaries`.Loops are used to do repetitive tasks.

**Syntax of For loop** :

```
for variable in iterable
    #loop body
```

- Loops Internally use **iterators** `(__iter__() & __next__())`
to process elements.

```
fruits=["apple","banana","cherry"] #this is the list
for fruit in fruits: # the for loop print the all element in the list in sequence wise
    print(fruit)
```

## Using `range()` in  `for` loops

```
for i in range(5):
    print(i)  # the range function intialize zero and go for the 4 
```
- `range(n)` generates numbers from `0 to n-1`.
- `range(start,stop,skip)` follow this.

```
for i in range(1,10,2): #start=1, stop=10, step =2 (skip the 2 element in this)
    print(i)
```

## **Iterate Over a String**

```
for char in "Python": # print the python in this sequence like p y t h o n
    print(char)
```

## **Looping Through a Dictionary**

```
data={"name":"Hi","age":21}:
for key,value in data.items():
    print(key, "->",value) #print the key and values
```

- use `.items()` to iterate over both keys and values.

# Using `continue` to skip an iteration

```
for i in range(5):
    if i==2:
        continue #skips the rest of the loops body  for i =2
    print(i)

```
- `continue` skips only the current iterations but keeps the loop running.

## **Nested Loops : Looping Inside a Loop**

```
for i in range(3):
    for j in range(2):
    print(f"i={i},j={j}")
```

- Nested loops are useful for processing `matrices and multidimensional data`

## Looping With `else`

```
for i in range(3):
    print(i)
else:
    print('loop completed') #the else block runs only if the loops completes with out a break statements. 
```

**When else does not execute**

```
for i in range(3):
    if i==1:
        break
    print(i)
    
else:
    print("Loop completed") #The else is not execute because for loop not run properly.
```

## Using List comprehension Instead of Loops
- It is more efficient and faster

```
square=[x**2 for x in range(5)]
```

## Using the `enumerate()` instead of `range(len())

```
fruits = ["apple", "banana", "cherry"]
for i, fruit in enumerate(fruits):
    print(i,fruit) #it print the index and value of the list.
```

## Using `zip()` for iterating Multile Sequences
```
name=['abc','bcd','def']
age=[25,30,35]
for name,age in zip(name,age):
    print(name, "is",age,"year old")
```

## Generator Expressions:
```
squares=(x**2 for x in range(5)) #use generator expression
```

## Break Statement

- With the `break` statement we can stop the loop before it has looped through all the items.

```
fruits=['apple','banana','cherry']
for x in fruits:
    print(x)
    if x=="banana":
        break
```

```
adj=['red','big','tasty']
fruits=['apple','banana','cherry']

for x in adj:
    for y in fruits:
        print(x,y)
```

## **Practice**
```
learning_topics=["variable","data types","control flow","functions","modules"]

for topic in learning_topics:
    print("- " + topic)
```

## **Learning Outcome**

- I learn about how to for loop work.
- for loop is used to iterable the conditions firstly the `initialization, declarations, executions`.
- By using the for loop we can easily access the element in the iterable(list,tuple,dictionaries.)
