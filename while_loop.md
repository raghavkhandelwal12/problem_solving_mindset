# **Task9 : While Loop**

- `while` loop : Repeats execution while a condition remains `True`.

## **While Loop Syntax**

```
while condition:
    #loop body
```

```
count=0 #intialize
while count<5: 
    print("count", count) 
    count+=1
```

- While loop is useful when the number of iterations is unknown.

## **Using `break` to exit a loop

```
num=1
while num<10:
    print(num)
    if num==5:
        break #exit the loop
    num+=1
```

## **Practice**

```
counter=0 #intialize counter variable
while True: # true until the condition is met
    user_input=input("enter the command(write exit to close the loop): ")
    counter+=1 #increase one

    if user_input.lower()=="exit": #exit to close the loop
        print(f"loop{counter} ")
        break
    
    print(f"write '{user_input}'")
```

## **Learning Outcome**

- To use the while loop provide the best for until the condition met.
- learn about the while loop syntax and how to define the while loop.
- After i learn about the while loop i write my problem.
