# **Task 11 - Parameters, Return Values, and Scope**

**Objective** : How to pass parameters, and how to return, learn about the local and global scope.

## **Arguments**

- Information can be passed into function as `arguments`.
- Arguments are specified after the function name, inside the parentheses. We can add as many argument as we want, but seperate the comma.

**Example**

```
def my_function(fname): #here only one argument fname
    print(fname + " hi")
my_function("abc") #print abc hi
my_function("bcd") #print bcd hi

```

## **Parameters or Arguments**

- The terms parameter and argument can be used for the same thing: `information that are passed into a function`.

**From a Function perspective** : 

- A `parameter` is the variable listed inside the parentheses in the function definition.
-  An `argument` is the value that is sent to the function when it is called.

## **Number of Arguments**

- By default, a function must be called with the correct number of arguments. Meaning that if our function expects 2 arguments, we call the function with 2 arguments,not more, and not less.

```
def my_function(fname,lname): # the function expect 2 argument
    print(fname + " " + lname)
my_function("raghav","khandelwal")

```

- If try to call the function with `1 or 3 arguments`, get the error.

```
def my_function(fname,lname):
    print(fname + " " + lname)
my_function("raghav") # this give the error because it have only one argument and the function definition two parameter

```

## **Arbitrary Arguments, *args**

- If we don't know how many argument that will be passed into the function, add a `*` before the parameters name in the function definition.
- This way the function will receive a tuple of arguments, and can access the items accordingly.

```
def my_function(*abc): # add * to add many parameter
    print("the younges child is " + abc[2]) 

my_function("ra","gh","av") # this print only the av

```

## **Keyword Arguments**
- We can also send arguments with the `key=value` syntax.
- The way the order of the argument does not matter.

```
def my_function(child3,child2,child1): #define the 3 parameter
    print("The youngest child is " + child3)

my_function(child1="abc",child2="bcd",child3="gfd")

```

## **Arbitary Keyword Argument, **kwargs**

- If don't know how many keyword arguments that will be passed into our function add two asterisk `**` before the parameter name in the function definition.
- This way the function will receive a dictionary of arguments, and can acces the items accordingly.

```
def my_function(**abc): # define the arbitary keyword arguments
    print("His last name is  " + abc["lname"])
my_function(fname='ab',lname='bcd')
```

## **Default Parameter Value**

- If we call the function without argument, it uses the `default value`.

**Example**

```
def my_function(country='India'): #define the default value India
    print("i am from " + country)
my_function("Nepal") # it print the nepal 
my_function() # It print the india because it take the default value
```

## **Passing a List as an Argument**

- We can send any data types of argument to a function(string,number,list,dictionary), and it will be treated as the same data type inside the function.

**Example**
```
def my_function(food):
    for x in food:
        print(x)
fruits=["apple","banana","cherry"]
my_function(fruits)
```

## **Return Values**
- To let a function return a value, use the `return` statement.

**Example**
```
def my_function(x):
    return 5 * x
print(my_function(3))
print(my_function(5))

```

## **The pass Statement**
- Function definitions cannot be empty, but if you for some reason have a `function` definition with no content, put in the `pass` statement to avoid getting an error.

```
def my_function():
    pass

```

## **Positional-Only Arguments**

- We can specify that a function can have only positional arguments, or only keyword argument.
- To specify that a function can have only positional arguments, add, `/` after the arguments.

**Example**
```
def my_function(x,/):
    print(x)
my_function(3)

```

- Without the `, /` actually allowed to use keyword arguments even if the function expects positional arguments.

```
def my_function(x):
    print(x)
my_function(x=3)

```

- But when adding the `, /` you will get an error if try to send the keyword arguments.

```
def my_function(x,/):
    print(x)
my_function(x=3) # this give the error give the keyword 

```

## **Keyword-Only Argument**

- To specify that a function can have only keyword arguments, add `*`, before the arguments.

**Example**

```
def my_function(*,x): # in this we add the keyword
    print(x)
my_function(x=3) # this is not give the error

```

- Without the `*,` you are allowed to use positionals arguments even if the function expects keyword arguments.

**Example**

``` 
def my_function(x):
    print(x)
my_function(3)

```

- But with the `*,` you will get an error if try to send a positional arguments

**Example**
```
def my_function(*,x):
    print(x)
my_function(3) #this give the error

```

## **Combine Positional-Only and Keyword-Only**

- We can combine the two argument types in the same function.
- Any argument before the `/,` are positiona only,and only argument after the `*,` are keyword only.

```
def my_function(a,b,/,*,c,d):
    print(a + b + c + d)
my_function(5,6, c=7,d=8)

```

## **Practice**

```
def add(a,b):
    return a + b
print(add(5,3))

```

## **Learning Outcome**

- Learn about the function bascis and function parameters 
- learn about the keyword argument and positional argument
- learn about the pass and combine argument.


