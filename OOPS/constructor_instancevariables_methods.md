# Task 2 : Constructor, Instance Variables & Methods

**Understanding the __init__ Method in Depth**

- In python `__init__` is special method(known as constructor) that calls automatically when an object is created. This is useful to `initialize instance variable` that belongs to an object.

1. **Role of __init__ in Object Oriented Programming(OOP)**

- Assign `default values` to object properties.
- Ensure each object has its own `separate state`.
- Improve code reusability to automatic process initialization.
- Allow `parameterized initialization` where object properties can be set at the time of creation.

**Note** : If we don't use the `__init__` we set the instance variable manually after creating an object which lead to inefficient and error-prone.

2. **__init__ in the context of classes and objects**

**Example**

```
class Student:
    def __init__(self,name,age):
    #initialization instance variable
        self.name=name
        self.age=age

    def display_info(self):
        print(f"Name:{self.name},Age:{self.age}")

#creating an object

s1=Student("abc",20)
s2=student(21,"abc")

#call the display_info method
s1.display_info()
s2.display_info()
```

**How Does __init__ Work Here?**

- When `s1=Student("abc",20)` is executed.
- Python calls the `__init__` method automatically.
- `sel.name="abc"` : Stores `abc` in `s1 name attribute`.

4. **self in __init__**

- The `self` parameter represents the `current object`.
- It allow the instance variable to `store the unique data`.
- Without `self`, Python don't know which object's attribute to assign.

**Example**

```
class Car:
    def __init__(self,brand,model):
        self.brand=brand
        self.model=model

#creating two objects
car1= Car("Toyota","abc")
car2=Car("Honda","civic")

print(car1.brand)
print(car2.model)
```

- Here, `self.brand` and `self.model` store `seperate values for car1 and car2`.

5. **__init__ with Default Argument**

- If we give the some default value we assign in the __init__ inside.

**Example**

```
class Employee:
    def __init__(self,name,salary=55555): #here salary is the default value
        self.name=name
        self.salary=salary
emp1=Employee("Amit") #here salary automatic print as default value
emp2=Employee("abc",30000)
print(emp1.name,emp1.salary)
print(emp2.name,emp2.salary)
```

# Method Overloading vs. Method Overriding

## Method Overloading

- `Method Overloading` occurs when multiple method in the same class share the same name but have `different number of parameter or different type of parameters.`

- Same method name but different signatures(parameters)
- Defined within the `same class`.
- Helps in increasing code readability and reusability.

**Note: Python does not support method overloading but we can achieve similar behavior using `default argument or *args`.**

**Example**

```
class Calculator:
    def add(self,a,b,c=0): # Default argument used to overload method
        return a+b+c
calc=Calculator()
print(calc.add(5,10))
print(calc.add(5,10,15))
```

## **Why Python Doesn't Support Method Overloading?**

- In python, we defines `multiple methods` with the same name, the latest definition `overwrites` the previous name.

**Example**
```
class Test:
    def show(self,a):
        print(a)
    
    def show(self,a,b) #this method overwrites the previous one
        print(a,b)

t=Test()
t.show(10,20) #works
t.show(10) #error (missing argument)
```

# Method Overriding

- Method overriding occurs when a `child class provides a specific implementation` of a method that is already define in its `parent class`.
- same method name and same parameters.
- Defined in `parent and child`.
- Helps in achieving `polymorphism`.

**Example of Method Overriding in Python**

```
class Animal: #this is parent class
    def speak(self):  
        print("animals make sound")

class Dog(Animal):
    def speak(self): #method overriding
        print("Dog barks")

#creating objects

a=Animal()
d=Dog()
a.speak()
d.speak()
```


**How Method Overriding Works?**

- The child class `overrides` the method the the parent class.
- if we want to access the overridden method of the parent class, we use the `super()`.

**Example**

```
class Animal:
    def speak(self): #parent method
        print("Animal make sound")

#child class (dog)
class Dog(Animal):
    def speak(self): #overridden parent method
        print("Dog barks")

#child class(cat)
class Cat(Animal):
    def speak(self):
        super().speak() #calls parent class method
        print("Cat meows")

#creating objects
a=Animal()
d=Dog()
c=Cat()

a.speak()
d.speak()
c.speak()
```

# Call by Value vs. Call by Reference

## Call by value

- A copy of the variable is passed to the function.
- Change made inside the function `do not affect` the origional value.
- Used in `immutable data type`(e.g., int ,float, str,tuple) in python.

**Example**

```
def change_value(x):
    x=10 # changing the copy, not the original variable
a=5
change_value(a)
print(a) #output 5(unchanged)
```

**Explanation** : 

- `a` is an integer(immutable).
- The function gets a `copy` of `a`, so the origional value remains unchanged.


## Call by Reference

- A `reference(address)` of the variable is passed to the function.
- Changes made inside the function `affect the origional value`.
- Used in `mutable data type(e.g. list, dict, set)` in python.

**Example**

```
def modify_list(lst):
    lst.append(4) #modifies the origional list

mylist=[1,2,3]
modify_list(mylist)
print(mylist)
```
**Explanation**

- `my_list` is a list(mutable)
- The function `modifies the original object ` instead of working on copy.

6. **Overloading __init__(multiple constructor)**

- Python does not support `method overloading` in the traditional sense, we can handle multiple cases using `default arguments` or `*args` and `**kwargs`.

**Example**

- Using Default values.

```
class Book:
    def __init__(self, title, author="unknown"):
        self.title=title
        self.author=author
b1=Book("Python basic") #author deault is unknown
b2=Book("Dsa","abc")
print(b1.title,b1.author)
print(b2.title,b2.author)
```

**Using *args and **kwargs**

```
class Product:
    def __init__(self,*args):
        if len(args)==2:
            self.name,self.price=args
        elif(len(args))==1:
            self.name=args[0]
            self.price=100  #default price
p1=Product("Laptop",50000)
p2=Product("Mouse")
print(p1.name,p1.price)
print(p2.name,p2.price)
```

7. **Modifying Instance Variables after object creation**

```
class Laptop: 
    def __init__(self,brand,price):
        self.brand=brand
        self.price=price

l1=Laptop("dell",60000)
print(l1.price)#output 60000

#modifying instance variables
l1.price=55000
print(l1.price)
<!-- print(l1) -->
```

8. **Using __init__ with Class Variable**

- `__init__` initialize `instance variables`. If we want `common variable` we use the `class variable`.

```

# class variable
class Person:
    company="Google"
    
    def __init__(self,name,age):
        self.name=name
        self.age=age
               
p1=Person("Abc",21)
p2=Person("Bcd",21)

print(p1.company) #output Google
print(p2.company) #output Google
```

- Here, `company` is shared among all objects, while `name and salary` are specific to each object.

9. **__init__ and Inheritence**

- In inheritance, the child class can use the `__init__` method of the parent class.

```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)  # Calls Parent class__init__
        self.student_id = student_id

s1 = Student("Aryan", 21, "S123")
print(s1.name, s1.age, s1.student_id)  # Output: Aryan 21 S123
```

- `super().__init__(name,age)` calls the parent classes `__init__`,prevent the code duplication.


# **Ques1 : Can we make constructor inside constructor**
- We can achieve the effect of calling a constructor within another constructor using `constructor chaning` or `nested object creation`.

1. **Constructor Chaning Using self.__init__()**

**Example: Reinitalizing an Object**

```
class Example:
    def __init__(self,x=None):
        if x is None:
            print("Default construcor is called")
        else:
            print("Parameterized constructor called")
            self.__init__() #calling the constructor again
obj=Example(10)
```
- The `first constructor call` prints `Parameterized constructor called`.
- The self.__init__() call `reinitialize the objects, so it print `Default constructor is called`.


# `@classmethod` in python

- A `@classmethod` in Python is a special types of method that is bound to the `class` rather than an `instance of the class`.It can access and modify `class-level attribute` but cannot modify instance-specific data.


1. **Syntax of `@classmethod`**

```
class ClassName:
    class_variable="shared data"

    @classmethod

    def class_method(cls):
        def class_method(cls):
            return f"Class method accessing:{cls.class_variable}"
```

- `@classmethod` `decorator` is used to define a class method.
- The first parameter `cls` refers to the `class itself` not an instance.

2. **Example : Using `@classmethod`**
```
class Animal:
    species = "Mammal"  # Class-level attribute

    @classmethod
    def change_species(cls, new_species):
        cls.species = new_species  # Modifies class variable

# Calling class method without creating an instance
print(Animal.species)  # Output: Mammal
Animal.change_species("Reptile")
print(Animal.species)  # Output: Reptile
```

**Explanation**

- The class method `change_species` modifies the `class variable species`.
- It is called directly on the class `(Animal.chage_species("Repetile"))` not an object.

3. **Example: Creating Object using `@classmethod`.

- A common use case of `@classmethod` is defining `alternative constructor`.
- An alternative constructor is simply a method that creates an instance of the class using a different approach than the standard `__init__` method. It is commonly used when we need to pre-process data before passing it to the constructor.

```
class Person:
    def __init__(self,name,age):
        self.name=name
        self.age=age

    @classmethod

    def from_birth_year(cls,name,birth_year):
        return cls(name,2025-birth_year) #calculating age from birth year

#creating instances using alternative constructor
p1=Person("Alice",25)
p2=Person.from_birth_year("Bob",2000)

print(p1.name,p1.age)
print(p2.name,p2.age)
```
**Explanation**

- `from_birth_year()` acts an `alternative constructor`.
- It creates an instance by claculating the age from the birth year.

4. **When to use `@classmethod`**
- Modify `class variables`(not instance variable).
- Implement `factory method/alternative constructor`.


# Understanding `@staticmethod` in Python

- A `@staticmethod` is a special method in python that `does not require access to class or instance attributes`. It behave just like a regular function but it is defined inside a class for better organization.

1. **Syntax of `@staticmethod`**
```
class ClassName:
    @staticmethod
    def method_name():
        #no self and cls is required
        print("This is a static method")
```
- `@staticmethod` **decorator** is used to define a `static method`.
- It does not take `self`(instance) or `cls`(class).
- It behaves like a normal function but is grouped inside a class.

2. **Example : Using `@staticmethod`**

```
class MathOperations:
    @staticmethod
    def add(x,y):
        return x+y

#calling static method without creating an instance
print(MathOperations.add(5,10)) #output is 15
```

3. **Difference between `@staticmethod` and `@classmethod`**

| Feature            | @classmethod              | @staticmethod              |
|--------------------|--------------------------|----------------------------|
| **Decorator**      | `@classmethod`           | `@staticmethod`            |
| **First Argument** | `cls` (refers to class)  | No `cls` or `self` required |
| **Accesses**       | Class-level attributes/methods | No class/instance variables |
| **Modifies**       | Can modify class variables | Cannot modify class or instance variables |
| **Use Case**       | Alternative constructors, modifying class attributes | Utility/helper functions |


4. **Example:Using `@classmethod` and `@staticmethod` together**

```
class Car:
    wheels=4 #class variables
    
    def __init__(self,brand,price):
        self.brand=brand
        self.price=price
    
    @classmethod
    def change_wheels(cls,change_wheels):
        cls.wheels=change_wheels
    
    @staticmethod
    def car_info():
        print("cars are used for driving:")
#using @staticmethod
Car.car_info() #print the cars are used for driving

#using @classmethod
print(Car.wheels)#output 4
Car.change_wheels(6) 
print(Car.wheels) #output6
```

**Explanation**
- `car_info()` is a static method because it does not interact with instance/class attributes.
- `change_wheels(cls,change_wheels)` is a class method because it modifies the `class variables` `wheels`.

5. **When to Use `@staticmethod?`**

- When we need a `utility/helper` function inside a class.
- The method is logically related to the class but `doesn't need class data.

6. **Real-World Example**

```
class TempratureConverter:
    @staticmethod
    def celsius_to_farenheit(celsius):
        return(celsius*9/5)+32

    @staticmethod
    def farenhite_to_celsius(farenheit):
        return(farenheit-32)*5/9

#using static method
print(TempratureConverter.celsius_to_farenheit(25))
print(TempratureConverter.farenhite_to_celsius(77))
```

# Instance Variable in Python

- Instance variables are variables that belongs to an instance of a class.They store unique data for each object and help maintain the objects independently.These variable are defined using the `__init__` method using `self`.

1. **Defining Instance Variable** : Instance variables are defined inside the consturctor `(__init__)` using `self`.

**Example**

```
class Module:
    def __init__(self,module_name,description,progress):
        self.module_name=module_name
        self.description=description
        self.progress=progress

#creating instances(objects)
module1=Module("Python Basics", "cover variable,data types",80)
module2=Module("OOP in python","class,object,constructor",70)

#accessing instance variable
print(module1.module_name)
print(module2.progress)

```
- Each object(module1,module2) has its own copy of `module_name,description, and progress` maintaining a unique a state.

2. **Accessing and Modifying Instance Variable** : We can access and modify instance variables directly using `object_name.variable_name`.

**Example**
```
module1.progress=80 #update the progress
print(module1.progress) #output 80
```

- we can also use instance method to modify instance variables safely.

```
class Module:
    def __init__(self,module_name,description,progress):
        self.module_name=module_name
        self.description=description
        self.progress=progress

    def update_progress(self,new_progress):
        self.progress=new_progress #update the progress 

#updating progress using method
module1=Module("Python basics","cover basic topic",80)
module1.update_progress(89)
print(module1.progress)
```

