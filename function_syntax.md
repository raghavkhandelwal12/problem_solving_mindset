# **Function- Definition and Basic Syntax & Dry Principle(Don't Repeat yourset)**

- **Objective** : What is Functions, syntax, and why it is use?

- A function is a `block of code which only runs when it is called.
- We can pass data, known as `parameters`, into a function.
- A function can return data as a result.
- Function are reusable blocks of code that enhance `modularity, efficiency, and readability`.

**In python a function is defined using the `def` keyword**.

```
def my_function(): #define the function 
    print("Hello")
```

## **Calling A function**
- To call a function names followed by parenthesis

```
def my_function():
    print("hello")
my_function()
```


**Returning Multiple Value(Tuple Return)**
```
def coordinates():
    return 10,20 # return a tuple
x,y=coordinates()
print(x,y)
```

## **Practice**

```
def greet():
    print("Welcome to the university wi-fi portal)
#call the function
greet()

```

## **Learning Outcome**

- In this task i learn about the how to define and calling the function
- I know about the function is define the using the `def` keyword.
- I know about the calling function if we define the function we easily call the function not write again and again it follow the dry principle`(don't repeat yourself)`.
