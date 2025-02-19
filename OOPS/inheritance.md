# Inheritance in Object-Oriented Programming(OOP)

- Inheritence is a fundamental concept in object-oriented programming(OOP) that allow a `class(child or derived class)` to acquire properties and behaviors(methods) from `another class(parent or base class)`.
- It promotes `code reusability, hierarchical classification, and extensibility.`

# Type of Inheritance

1. `Single Inheritance` : one child class inherits from a single parent class.

**Example**

```
class Parent: #this is a parent class
    def display(self):
        print("This is the parent class")

class Child(Parent): #this is a child class
    pass #inherits display() method from parent

obj=Child()
obj.display()
```

2. `Multiple Inheritance` : A child class inherits from more than one parent class.

```
class Parent1:
    def method(self):
        print("Method from parent1")
    
class Parent2:
    def method(self):
        print("Method from parent2")

class Child(Parent1,Parent2):
    pass

obj=Child()
obj._Parent1__method()
obj._Parent2__method()
```

3. `Multilevel Inheritance` : A child class inherits from another child class.

**Example**

```
class Grandparent:
    def grand_method(self):
        print("Gradparent class")

class Parent(Grandparent):
    def parent_method(self):
        print("Parent class")

class Child(Parent):
    def child_method(self):
        print("Child class")

obj=Child()
obj.grand_method()
obj.parent_method()
obj.child_method()
```

4. `Hierrarchical Inheritance` : Multiple child class inherits from a single parent class.

```
class Parent:
    def show(self):
        print("Parent class")

class Child1(Parent):
    pass

class Child2(Parent):
    pass

obj1=Child1()
obj2=Child2()
obj1.show()
obj2.show()
```

5. `Hybrid Inheritance` :  A combination of multiple types of inheritance.

```
class Base:
    def base_method(self):
        print("Base class")

class Derived1(Base):
    def derived1_method(self):
        print("Derived1 class")

class Derived2(Base):
    def derived2_method(self):
        print("Derived2 class")

class Child(Derived1, Derived2):
    def child_method(self):
        print("child class")

obj=Child()
obj.base_method()
obj.derived1_method()
obj.derived2_method()
obj.child_method()
```

# Method Overriding

- When a child class redefines a method from the parent class.

```
class Parent:
    def show(self):
        print("Parent class method")

class Child(Parent):
    def show(self):
        print("Child class Method")

obj=Child()
obj.show() #calls the overridden method from child
```

# The `super()` Function

- Use to call a method from the parent class.

```
class Parent:
    def show(self):
        print("Parent class method")

class Child(Parent):
    def show(self):
        super().show() #call the parent class method
        print("Child class method")

obj=Child()
obj.show()

```

# Constructor Inheritance `(__init__)`
- The child class can call the parent class constructor using `super()`.

```
class Parent:
    def __init__(self,name):
        self.name=name

class Child(Parent):
    def __init__(self,name,age):
        super().__init__(name) #calling parent constructor
        self.age=age

obj=Child("ABC",20)
print(obj.name,obj.age)
```

# Advantage of Inheritance

- `Code Reusability` : Reduces duplication by allowing reuse of existing code.
- `Extensibility` : Allow modifications and extensions to existing classes.
- `Modularity` : Helps in organize and structure code efficiently.
- `Maintainability` : Easier to manage and update code.

# Real-World Example of Inheritance

- `Vehicle Inheritance Model`

```
class Vehicle:
    def __init__(self,brand):
        self.brand=brand
    
    def show(self):
        print(f"this is a {self.brand} vehicle")

class Car(Vehicle):
    def __init__(self,brand,model):
        super().__init__(brand)
        self.model=model
    
    def details(self):
        print(f"car brand:{self.brand},Model:{self.model}")

obj=Car("Toyota","Camry")
obj.show()
obj.details()
```

- Here, `Car` inherits from `Vehicle` while adding its own `details()` method.


# Public, Private, and Protected Members in Python

- Python follows and `object-oriented programming(oop) paradigms`, where data is encapsulated within the `class`. To enforce `data protection`, Python provides three types of access modifiers.

1. `Public` : Accessible to anywhere
2. `Protected` : Accessible only within the class and its subclass(by convention).
3. `Private` : Accessible only within the class

1. `Public Members` : Public attributes and methods are accessible from anywhere, inside or outside the class.
- `Syntax`: No special prefix `(_ or __)`.
- `Usuage` : Used when data and method needs to be available to all parts of the program.

**Example**
```
class Student:
    def __init__(self,name,age):
        self.name=name #Public attribute
        self.age=age #public attribute

    def display(self): #public method
        print(f"Name:{self.name},Age:{self.age}")

#creating an objects
student1=Student("Raghav",22)

#accessing public attribute

print(student1.name)
print(student1.age)

#calling public method
student1.display()
```
- `name` and `age` are `public attribute` that can accessed from `anywhere`.
- `display()` is a `public method` and can be called from `outside the class`.

2. `Protected Members(_single_underscore)` : Protected attributes and method can be accessed `within the class and its subclass`.
- `Syntax` : Prefix the attribute or method with a single undersocre `(_)`.
- `Usuage` : Used when attribute/methods should not be modified directly but should still accessible within subclass.

**Example**

```
class Parent:
    def __init__(self):
        self._protected_var=42 #protected attribute

    def _protected_method(self): #protected method
        print("this is a protected method")

#child class(inherits from Parent)

class Child(Parent):
    def access_protected(self):
        print(f"Accessing protected var:{self._protected_var}")
        self._protected_method()

#object creation
obj=Child()
obj.access_protected()

#access protected member outside the class

print(obj._protected_var)
print(obj._protected_method)

```

3. `Private Members(__double_underscore)`: Private attribute and method cannot be accessed directly outside the class.
- `Syntax` : Prefix the attribute or method with a double underscore `(__)`
- `Usuage` : Used when data should be `hidden from the external access`(e.g password, sensitive information).

**Example**

```
class BankAccount:
    def __init__(self,account_holder,balance):
        self.account_holder=account_holder #public attribute
        self.__balance=balance #private attribute

    def deposit(self,amount): #public method
        if amount>0:
            self.__balance+=amount
            print(f"Deposited {amount}. New Balance:{self.__balance}")
        
        else:
            print("Invalid deposit amount")
    
    def __private_method(self):
        print("this is a private method")

#object creation
account=BankAccount("abc",300000)
print(account.account_holder) #accessible public
```

# Apply the Inheritance in Project

```
#Base class for Module
# Base Class for Modules
class Module:
    def __init__(self, name, description, progress=0):
        self.name = name
        self.description = description
        self.progress = progress

    def show_info(self):
        print(f"\nModule: {self.name}\nDescription: {self.description}\nProgress: {self.progress}%")

    def update_progress(self, progress):
        self.progress = progress
        print(f"Progress for {self.name} updated to {self.progress}%.")

# Subclass for Variables Module
class VariablesModule(Module):
    def __init__(self, description, progress=0):
        super().__init__("Variables", description, progress)

    def show_info(self):
        super().show_info()
        print("Tip: Variables store data and help us manage values dynamically!")

# Subclass for Control Flow Module
class ControlFlowModule(Module):
    def __init__(self, description, progress=0):
        super().__init__("Control Flow", description, progress)

    def update_progress(self, progress):
        if 0 <= progress <= 100:
            super().update_progress(progress)
        else:
            print("Error: Progress must be between 0 and 100.")

# Creating Objects
var_mod = VariablesModule("Learn about variables and data storage.")
var_mod.show_info()
var_mod.update_progress(40)

ctrl_mod = ControlFlowModule("Understand loops and conditionals.")
ctrl_mod.show_info()
ctrl_mod.update_progress(110)  # Invalid input handled

```


# Diamond Problem in Inheritance

- The diamond problem is a common issue in multiple inheritance where a class inherits from two or more classes that share a common ancestor. This can create ambiguity in the `Method Resolution Order`.

## Why is it called the `Diamond Problem?`

- The `class hierarchy forms a diamond shape` as shown below.

```
        A
       / \
      B   C
       \ /
        D
```
- `B` and `C` both inherit from `A`.
- `D` inherits from `both` `B` and `C`.

**Example**

```
class A:
    def show(self):
        print("Class A")

class B(A):
    def show(self):
        print("Class B")

class C(A):
    def show(self):
        print("Class C")

class D(B,C): #multiple inheritance
    pass

obj=D()
obj.show()
```
