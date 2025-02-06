# **Task 7 : Conditional Statements(if, elif, else)**

- **Objective** : For Decision making we must know about the `control flow`.

**Example**
```
a=33
b=200
if b>a:
    print("b is greater than a")
```

- If we not follw the proper indentation refer to the error.
```
a=33
b=200
if b>a:
print("b is greater than a") #This give the error because it is not follow the proper indentation.
```

# **Elif** : 

- The `elif` keyword is Python's way of saying "if the previous conditions were not true, they try this condition.

```
a=33
b=33
if b>a: #This condtion is not true it go to the next condtion
    print("b is greter than a")
elif a==b:
    print("a and b are equal") # if the this condition is true than it execute the condition 
```

# **Else**

- The `else` keyword catches anything which is not caught by the preceding conditions means that if the condition is false than it execute the else condtions.

```
a=200
b=33
if b>a:
    print("b is greater than a")
elif a==b:
    print("a and b are equal")
else:   
    print("a is greater than b")
```

- We can also use the `else` without the `elif`

```
a=200
b=33
if b>a:
    print("b is greater than a")
else:
    print("a is greater than b")
```

**Short Hand If** : If you have only one statement to execute, we can put it on the same line as the if statement.

```
if a>b: print("a is greater tha b")

```

**Short Hand if...else** : If we have only one statement to execute, one for if, and one for else, you can put it all on the same line.

```
a=2
b=330
print("A") if a>b else print("B") # This technique is called the Ternary Operators or condtional expressions.

```

- We can also have multiple else statements on the same line
```
a=220
b=220
print("A") if a>b else print("=") if a==b else print("B") # this give the = because it is not greater the a to b 
```

- `And` : The and is logical operator and we use it in the control-flow.

```
a=200
b=33
c=1
if a>b and b>c: #this give the if the both the conditions are true
    print("Both conditions are True")
```

- `Or` : The `or` operator is used when at least one condtion is true.

```
a=200
b=33
c=11
if a>b or c>b:
    print("result")
```

**Nested If**: We can have `if` statement inside `if` statement. It means that we can use the if inside if called the `nested if`.

```
x=30
if x>10:
    print("above child")
    if x>20:
        print("adult")
    else:
        print("not adult")
```

**Pass Statement** : `if` statement cannot be empty, but if we for some reason have `if` statements with no content, put in the `pass statement` to avoid getting error.

```
a=33
b=200
if b>a: # This give the error because we not write in below if

```

**Using the pass statement**

```
a=33
b=300
if b>a:
    pass # this not give the error
```

# Practice
```
marks=int(input("enter the student marks"))
if marks>90: 
    print("Good")
elif marks>70 and marks<80:
    print("Excellent")
elif marks>35 and marks<60:
    print("Need Improvement")
else:
    print("Fail")
```

# **Outcome** : 

- I learn about the conditional statement 
- I learn by using the if-else i make the my condition which i want to execute if the condition is true.
- After i learn about the nested if statement.
- After i learn about the shorter syntax of the if-else statement.
