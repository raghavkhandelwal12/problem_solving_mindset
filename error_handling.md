# **Task 14: Error Handling- try,except, finally**

**Objective** : Exception handling importance

## **Python Try Except**

- The `try` block lets to test a block of code for errors.
- The `except` block let to handle the error.
- The `else` block lets to execute code when there is not error.
- The `finally` block let to execute code, regardless of the result of the `try-and except blocks`.

## **Exception Handling**

- When an error occurs, or exception as we call it, Python will normally stop and generate an error message.
- These exceptions can be handled using the `try` statement.

**Example**

- The `try` block will generate an exception, because `x` is not defined.

```
try:
    print(x) # the x is not define then it go except block and execute the an exception occured
except:
    print("An exception occured")
```

- Without the `try` block, the program will crash and raise an error.

## **Many Exceptions**:
- We can define as many exception blocks as we want, e.g. if we want to execute a special block of code for special kind of error.

**Example**

- Print one message if the try block raises a `NameError` and another for other errors.

```
try:
    print(x)
except NameError:
    print("variable x is not defined")
except:
    print("something else went wrong")
```

## **Else**

- We can use the `else` keyword to define a block of code to be executed if no errors were raised.

**Example**

- In this example, the `try` block does not generates any error.

```
try:
    print("Hello")
except:
    print("something went wrong")
else:
    print("Nothing went wrong")

```

## **Finally**
- The `finally` block , if specified, will be execute regardless if the try block raises an error.

**Example**

```
try:
    print(x)
except:
    print('something went wrong')
finally:
    print('the try except is finished')

```

- This can be useful to close objects and clean up resources.


**Example**

```
try:
    f=open("demofile.txt") #make the txt file
    try:
        f.write("abc")
    except:
        print("something went wrong when writing to the file")
    finally:
        f.close()
except:
    print("something went wrong then opening the file")

```

## **Raise an exception**

- As a Python developer we can choose the throw an exception if a condition occurs.
- To throw(or raise) an exception, use the `raise` keyword.

**Example**

- Raise an error and stop the program if x is lower than 0:

```
x=-1
if x<0:
    raise Exception("sorry no number below zero") #give the error
```

- The `raise` keyword is used to raised an exception.
- We can define what kind of error to raise, and the text to print the user.

```
x="hello"
if not type(x) is int:
    raise TypeError("only intgers are allowed")

```

## **Practice**

```
def get_valid_number():
    while True:
        try:
            num = int(input("Ek number enter karein: "))  # User input
            print(f"enter {num} ")  # Valid input case
            return num  
        except ValueError:
            print("invalid input only number allowd.")  
```
