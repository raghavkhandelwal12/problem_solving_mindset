# Task 5 : **Other Data Types: Lists, Tuples, and Dictionaries**

- **Objective** : Learn about the `List, Tuple, Dictionary, Set`.

- `List` is ordered, mutable, and allow duplicate values.

## **Practice**

```
list=["Variable", "Data Types", "Control Flow"]
print(list)
list.append("Error handling") # Apppend the list means add the item in the end of the list
list.sort() #sort the list in the ascending order
list.remove("Data Types") # Remove the data types from the list
print(list)
print(list[0]) # Print the 0 index number 
list[0]="Operators" # replace the items with this items this is change the list items.
print(list)
```

## Learning Outcome to use the list

- By using the list we can easily `add or remove the items` in the list which i show in the above 
- And i learn about different types of list method.
- I learn about the list indexing by using the indexing technique we can easily access the list elements.
- `List Comprehesnion` : I learn about the list comprehension which is used to shorter syntax of the list
- And we can change the list items from the list

# Tuple
- Tuple are used to store multiple items into single variable. `Tuple are immutable, ordered and allow duplicate values`.

```
project_feedback=(
    ("Variables", "Not started"),
    ("Data Types", "Completed"),
    ("Control Flow", "In Progress")\

)

print("\n project Feedback(tuple):")
print(project_feedback)
```

## Learning Outcome
- Tuple is similar to like list but this main property is `immutable collection` which make it flexible compare to list.
- Tuple is also index we can easily access the element by using the index number.

- In tuple `basically there are two types of method

1. `Count Method` : Count the values appears in the tuples.
2. `Index Method` : Index value give the particular index 


# **Dictionary**

- `Dictionary` are used to store data in `key-value pairs.`

```
topic_status = {
    "Variables": "Completed",
    "Advanced Data Types": "Not Started",
    "Control Flow": "In Progress",
    "Functions": "Not Started"
}
print(topic_status) #print all the topic_status in the dictionary format.

```

## **Learning Outcome** : 

- I learn about the concept about the dictionary. Dictionary is provide the structured way to store the data.
- It is order,changeable but don't allow duplicate values.
- We can change the dictionary by give the key and assign the values.


# **Sets**

- Sets are unordered, and don't allow duplicate values.

```
books={"Python Books","Python Books", 1, 0, True, False}#Remove the duplicate values.
books.add(4) # add the item in the set
print(books)
additional_books={"Python Books",1}
x=books.intersection(additional_books) # this return the common part that come both sets.

print(x)
```

## **Learning Outcome** : 
- In set we can `add` the item easily items in the list.
- In set we easily `remove` in the set.
- We perform some `operation` which is related to the `mathematics`.





