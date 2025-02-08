# **Task 13 : Python Modules & Importing**

**Objective** : Built in modules `math`, `datetime` and how to use modules after creating.


## **Python Module**

**What is a Module** ?

- A module to be the same as code library.
- A file containing a set of functions we want to include in our applications.

## **Create a Module**

- To create a module just save the code we want to file with the file extension `.py`


**Example**

- Save this code in a file name `mymodule.py`.

```
def greeting(name):
    print("Hello, " + name)
``` 

## **Use a Module**

- We can use the module we just created, by using the `import` keyword.

**Example**

```
import mymodule
mymodule.greeting("Jonathan") # This print the Hello, Jonathan

```

**Note** : When using a function from a module, use the syntax:
`module_name.function_name`.


## **Variables in Modules**

- The modules can contain functions, as already described, but also variables of all types(array,dictionary,objects etc)

**Example**

```
person1={
    "name":"abc",
    "age":23,
    "country":"India"
}
```

**Example**
```
import module
a=module.person1["age"] #this print the 23
print(a)

```

## **Naming a Module**
- We can name the module file whatever we like, but it must have the file extension `.py`.

## **Re-naming a Module**

- We can create an `alias` when you import a module, by using the `as` keyword.

**Example**

```
import module as mx # renmaing the module mx 
a=mx.person1["age"]
print(a)

```

## **Built-in Modules**

- There are several built-in modules in python, which we can import whenever we like.

**Example**

```
import platform
x=platform.system() #this print the platform that you are working like window,linux, macos
print(x)

```

## **Using the `dir()` function

- There is a built-in function to list all the function names(or variable names) in a module. The `dir()` function.

**Example**
- List all the defined names belonging to the platform module.

```
import platform
x=dir(platform)
print(x)

```

- **Note** : The `dir()` function can be used on all modules, also the ones to create yourself.


## **Import From Module**

- We can choose to import only parts from a module, by using the `from` keyword.

**Example**
- The module named `module` has one function and one dictionary.
## **Practice**
```
def greeting (name):
    print("Hello, " + name)
person1={
  "name": "John",
  "age": 36,                        #save this code in the module.py
  "country": "Norway"
}
```

```
from module import person1
print(person1['age'])
```

## **Learning Outcome**

- Learn about how to use the module in my code.
- Learn about several built in functions.
