# **Task 15 : File I/O - Reading and Writing Files**

- **Objective** : How to read and write in the files data?

## **Python File Open**

- `File handling` is an important part of any web application.
- Python has several functions for `creating, reading, updating and deleting files.`.

## **File Handling**

The key function for working with files in Python is the `open()` function

- The `open()` function take two parameters; `filename` and `mode`.
- There are four different method(modes) for opening a file.

- `r` - Read- Default value. Opens a files for reading, error if the files does not exist.
- `a` - Append- Opens a file for appending, creates the file if it does not exist.
- `w` - Write- Opens a files for writing, create the file if it does not exist.
- `x` - Create - Create the specified file, returns an error if the file exists.

- In addition we can specify if the file should be handled as `binary or text mode`.

- `t` - Text- Default value. Text mode
- `b` - Binary- Binary mode(e.g images)


## **Syntax**

- To open a file for reading it is enough to specify the name of the file.

```
f=open("demofile.txt") # open a file in read mode.

```
- The code above is the same as:

```
f=open("demofile.txt","rt")

```

- Because `r` for read, and `t` for text are default values.

**Note** : Make sure the file exists, or else we get an error.


## **Python File Open**

### **Open a File on the Server**

- Assume we have the following file, located in the same folder as python.

- To open the file, use the built-in `open()` function.

- The `open()` function returns a file object, which has a `read()` method for reading the content of the file.

```
f=open("demofile.txt","r") #open the txt file in read mode and print the content of the file
print(f.read()) # this print the read mode file.

```

- If the file is located in different location, we will have to specify the file path, like this:

**Example**

- Open a file on a different location

```
f=open("D://myfiles/welcome.txt","r")
print(f.read())

```

## **Read only parts of the File**

- By default the `read()` method returns the whole text, but we can also specify how many character we want to return.

**Example**

- Returns the 5 first character of the file

```
f=open("demofile.txt","r")
print(f.read(5)) #print the five character of the file 

```

## **Read Lines**

- We can return one line by using the `readline()` method.

**Example**

- Read one line of the file.

```
f=open("demofile.txt","r") #open the file in read mode
print(f.readline(),end="") #print the first line 
print(f.readline(),end="") #print the second line
```

- By `looping` through the lines of the file, we can read the whole file, line by line.

**Example**

- Loop through the file line by line:

```
f=open("demofile.txt","r") # open the file in the read mode
for x in f:
    print(x,end="") #print the line without space.
```

## **Close Files**

- It is good practice to always close the file when you are done with it.

**Example**
- Close the file when we are finished with it.

```
f=open("demofile.txt","r") #open the file in read mode
print(f.readline())#print the single line
f.close() #close the file
```

**Note** : You should always close the files. In some cases, due to buffering, changes made to a file may not show until we close the file.

## **Python File Write**

### **Write to an existing file**

- To write an existing file, we must add a parameter to the `open()` function.
- `a` - Append- will append the end of the file.
- `w` - Write- will overwrite any existing content.

**Example**

- Open the file `example.txt` and `append` content of the file.

```
f=open("example.txt",'a') #append the content of the file 
f.write("hi hello this is my file")
f.close()

#open and read the file after the appending
f=open("example.txt",'r') #open the file in read mode
print(f.read()) # read the file
```

**Example**
```
f=open("example.txt",'w')
f.write("I have deleted the content") # overwrite the content if the content exist
f.close() #close the file

#open and close the file after the overwriting
f=open("example.txt",'r')
print(f.read()) #read the file content
```

**Note** : The `w` method will overwrite the entire file.

## **Create a New File**

- To create a new file in Python, use the `open()` method, with one of the following parameters.

- `x` - `Create` - will create a file, return an error if the files exist.
- `a` - `Append` - will create a file if the specified file does not exist.
- `w` - `Write` - will create a file if the specified files does not exist.

**Example**
```
f=open("myfile.txt",'x') # create teh file if not exist using the x and a empty file is created.
```

**Example**
- Create a new file if it does not exist.

```
f=open("abc.txt",'w') #create the file in write mode
```

## **Python Delete File**

### **Delete a File**

- To delete a file, we must import the `OS`module, and runs its `os.remove()` function.

**Example**

```
import os
os.remove('abc.txt')
```

## **Check if File exist**:

- To avoid getting an error, we want to check if the file exist before try to delete it.

```
import os
if os.path.exists("demofile.txt"):
    os.remove("demofile.txt")
else:
    print("The file does not exitst")
```

## **Practice**

```
import json

# --- Step 1: Define Student Progress ---
student_progress = {
    "Variables": "Completed",
    "Data Types": "Completed",
    "Control Flow": "In Progress",
    "Functions": "Not Started",
    "OOP": "Not Started",
    "Modules": "Not Started",
    "Error Handling": "Not Started"
}

# --- Step 2: Write to a Text File ---
text_file = "progress.txt"
with open(text_file, "w", encoding="utf-8") as file:
    for topic, status in student_progress.items():
        file.write(f"{topic}: {status}\n")
print(f"Student progress written to '{text_file}'.")

# --- Step 3: Read from the Text File ---
with open(text_file, "r", encoding="utf-8") as file:
    print("\nContent of the text file:")
    print(file.read())

# --- Step 4: Write to a JSON File (Optional) ---
json_file = "progress.json"
with open(json_file, "w", encoding="utf-8") as jf:
    json.dump(student_progress, jf, indent=4)
print(f"\nStudent progress written to JSON file '{json_file}'.")

# --- Step 5: Read from the JSON File ---
with open(json_file, "r", encoding="utf-8") as jf:
    progress_data = json.load(jf)
    print("\nContent of the JSON file:")
    for topic, status in progress_data.items():
        print(f"{topic}: {status}")
```

## **Learning Outcome**

- I learn about the file handling 
- how to read and modify the files.
