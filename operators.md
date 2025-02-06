## **Task 6 : Operators : Arithmetic, Assignment, Comparison, Logical and other operators**

- **Objective** : understanding the operators syntax what the particular use of the operators.


**Arithmetic Operaotrs** : Perform the calculation of the operands.

```
a=6
b=8
print(a+b) # perform the addition
print(a-b) # subtract  the a and b
print(a*b) # print the a multiple by b
print(a**b) #print the power of a,b
print(a//b) # print the floor division like if divide the 5/2 then it is give 2
print(a%b) # it give the remainder of the a and b
```

**Assignment Operator** : Use the assign the variable.
```
a=5
a+=2 # add  two in the a
a-=2 # subtract the two in a
a*=2 # a is multiply by 2
a/=2 # a is divide by 2
a//=2 # a is give the floor division
a%=2 
print(a) # print the final a 
```

**Comparison Operators** :  Comparison operators is used to compare the values.

```
a=2
b=1
print(a>b) # give the True
print(a<b) # give the False
print(a!=b) # This give the True
print(a>=b) # this give the true
```

**Bitwise Operator** : Bitwise operators is used to compute the calculation in bit level

```
a=5
b=4
print(a&&b) #It compute the and operator if both condition is true then it is give true
print(a||b)
print(~a) #it give the opposite like if i give the True it make False and vice Versa.
```

**Logical Operators** : Logical operator is used to make the decision.

## Practice:
```
marks=int(input("enter the your marks"))
attendance=int(input("enter your attendence"))
if marks>=89 and attendance>=75: #give the result if the both condtion is True
    print("pass")
else:
    print("Fail")
```

- In `logical` operator we also use the `or , not` operators.

**Membership Operators** : Memberhip operator is used when the two variable go to the same object.

```
a=53
b=a
if a is b:
    print("equal")
else:
    print("Not equal")
```

**Identity Operators** :  Check that the element in or not

```
a=[1,2,3,4]
if 1 in a: 
    print(1)
