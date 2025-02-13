# **Class and Objects in Python: A Deep Dive**

**What is a Class?**

- A class is a blueprint for creating objects.It encapsulates the `data(attribute)` and `behaviour(methods)` into a single unit.

**What is an Object?**

- An `object` is an instance of a class.
- When a `class` is defined `memory is not allocated`. `Memory only allocated` when an `object` is created.

## **Ques1: Difference between class variable and instance variable**

- In **oops**, variables in a class are divide into `class variables` and `instance variable` based on their scope.

**What is a Class Variable?**

- A `class variable` is a variable that is `shared among all instance of a class`. It defines `inside the class but outside any method`.
- Changing its values affects `all objects of the class`
- `Accessed` using the `class name(ClassName.variable) or an instance(self.variable)`.

**Example**

```
class Student:
    school_name="ABC School" # Class Variable(available to all object)

    def __init__(self,name,grade):
        self.name=name #instance variable
        self.grade=grade #instance variable

#creating instance
s1=Student("Raghav","A") # create object s1
s2=Student("ABC","B")    #create object s2

print(s1.school_name) #Output ABC School
print(s2.school_name) # output ABC School

#changing class variables

Student.school_name="XYZ School"
print(s1.school_name) # output: xyz school
print(s2.school_name) #output : xyz school

```

- **Note** : When we change `Student.school_name`, it updates for all instances.


**What is an Instance Variable?**

- An `instance variables` is a variable that is `unique` to each `instance(object)` of a class. It is defined `inside the __init__()` constructor using `self`,each object has its own seperate copy.
- changing an instance variable only affect that particular object.
- `Accessed` using `self.variable_name` inside the class.

**Example**

```
class Student:
    def __init__(self,name,grade):
        self.name=name #Instance variable
        self.grade=grade #instance variable

# creating instances

s1=Student("Raghav", "A")
s2=Student("ABC","B")
print(s1.name)

#Changing instance variable for s1 only

s1.name="acd"
print(s1.name)

```

- **Note** : Each object has its own copy of instance variable.If i change one object does not affect the other.


**Ques2: `Compilation Time vs. Runtime in Class**

- `Compilation Time` : When a class is defined, Python compiles the `class definition into bytecode before execution.

- `RunTime` : The objects is created, methods are called, and attribute `are accessed during runtime`.

**Example**

```
class Student:
    def __init__(self,name):
        self.name=name  #Runs at runtime when an object is created

s1=Student("Alice") #object creation happens at runtime

```

- The `class definition` is parsed at `compile time`, but object `creation and execution` happens at `runtime`.



**Ques3 : Can we define a class without using the `class` keyword in Python?**

- Technically, we can define a class without using the `class keyword` in python by using `type metaclass` dynamically.

## **Defining a Class Normally(using `class`)**

```
class Student:
    def __init__(self,name):
        self.name=name
s1=Student("abc")
print(s1.name)
```

## **Defining a Class Without Using `class` `(using type)`

- We can create a class dynamically using the `built-in type()` function.

**Syntax of `type()` for `Dynamic class creation**

```
ClassName=type("ClassName",(BaseClasses,), {attributes})
```

- `ClassName` : Name of the class.
- `(BaseClasses,)` : Tuple of base classes(can be empty for no inheritence).
- `{attribute}` : Dictionary containing methods and attribute.

**Example**

```
#Defining a class dynamically without using class

Student=type("Student",(),{"School":"XYZ School"})
#Creating an instance of the dynamically created class

s1=Student()
print(s1.school)

```

## **Adding Methods to the Dynamically Created Class**

- we can define methods inside a class created using `type()`

**Example**
```
def __init__(self, name):
    self.name = name

def display(self):
    return f"Student Name: {self.name}"

# Creating class dynamically
Student = type("Student", (), {"__init__": __init__, "display": display})

# Creating an instance
s1 = Student("Raghav")

# Calling method
print(s1.display())  # Output: Student Name: Raghav


```

**question4 : Can the `class` is compulsory to create object in Python**

- This is not compulsory to create an object by using the class.

- **Using a class without creating an Object** : We can define `class method` or `static method` that do not require an object.

**Example**

```
class Utility:
    @staticmethod
    def greet():
        return "hello, world"
print(Utility.greet()) #calling without creating an object.
```

- **Using a Class as a Namespace** : 

**Example**

```
class Config:
    DEBUG=True
    Version= "1.0.0"

print(Config.Version) # accessing attribute without class

```

- **Ques : When to Use a Class**

- When Working with objects that hold the `attribute and method`.
- When we want `encapsulation, inheritance, and polymorphism`.
- When dealing with `complex logic` that need to be structured.

**Example**

```
class Car:
    def __init__(self,brand,model):
        self.brand=brand
        self.model=model
    def display(self):
        print(f"Car:{self.brand},Model:{self.model}")

car1=Car("abc","bcd")
car1.display()
```  

- **Ques : When to Avoid Using a Class**

- When working with `simple scripts where a function` is enough .
- When we need only a single function.

**Example**

```
def add(a,b):
    return a+b
print(add(5,10)) #no need for a class, a function is sufficient.

```

