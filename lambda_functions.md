# **Task 12 : Lambda function & Higher Order Functions**

**Objective** : Anonymous function(Lambda) and use the practical .

- A lambda function si a small `anonymous function`.
- A lambda function can take any number of arguments, but can only have one expression.

**Syntax**

```
lambda arguments: expression

```

```
x=lambda a:a+10
print(x(5))
```

- Lambda functions can take any number of arguments.

**Example**

```
x=lambda a,b : a*b
print(x(5,6))

```

```
x=lambda a,b,c:a+b+c
print(x(5,6,2))
```

## **Why Use Lambda Function?**

- The power of lambda is better shown when we use them as an anonymous function inside another function.
- You have a function definition that takes one argument,and that argument will be multiplied with an unknown number.

```
def myfunc(n):
    return lambda a: a*n
mydoubler=myfunc(2)
print(mydoubler(11))
```

```
def myfunc(n):
      return lambda a : a * n

mydoubler = myfunc(2)
mytripler = myfunc(3)

print(mydoubler(11))
print(mytripler(11))
```

## Using Lambda with `map()`

```
numbers=[1,2,3,4]
squared=list(map(lambda x:x**2,numbers))
prnt(squared)
```

## Using Lambda with `filter()`

```
evens = list(filter(lambda x: x % 2 == 0, numbers))
print(evens)
```

## **Practice**
```
numbers=[1,2,3,4]
squared=list(map(lambda x:x**2,numbers))
prnt(squared)
```

## Learning Outcome

- Learn about the lambda function it is use to simple define function
- It uses to define the function in one line.
