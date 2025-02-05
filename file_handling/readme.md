## **Complete Guide to File Handling in Python (Including Advanced Methods)**  

### **What is File Handling?**  
File handling allows Python programs to store, retrieve, and manipulate data in files. This is crucial for **data persistence, logging, configuration management, and processing large datasets**.

---

## **1. Opening a File**  
Python provides the `open()` function:  
```python
file = open("example.txt", "r")  # Opens file in read mode
```
### **File Opening Modes**  
| Mode | Description |
|------|------------|
| `"r"` | Read (default, error if file not found) |
| `"w"` | Write (creates a new file, overwrites if exists) |
| `"a"` | Append (adds data at the end) |
| `"x"` | Exclusive creation (fails if file exists) |
| `"rb"` | Read in binary mode |
| `"wb"` | Write in binary mode |

---

## **2. Reading a File**  
```python
with open("example.txt", "r") as file:
    content = file.read()   # Reads entire file
    line = file.readline()  # Reads one line
    lines = file.readlines()  # Reads all lines as a list
```

---

## **3. Writing to a File**  
### **Overwrite File (`"w"`)**
```python
with open("example.txt", "w") as file:
    file.write("Hello, World!")
```
### **Append to File (`"a"`)**
```python
with open("example.txt", "a") as file:
    file.write("\nAppending more text.")
```

---

## **4. Working with Binary Files**  
For images, PDFs, etc.:
```python
with open("image.jpg", "rb") as file:
    data = file.read()
```

---

## **5. File Positioning Methods**  

### **`seek(offset, whence)` - Move Cursor to Specific Position**
- `offset` → Number of bytes to move.
- `whence` → Reference point:
  - `0` → Start of file (default)
  - `1` → Current position
  - `2` → End of file  

```python
with open("example.txt", "r") as file:
    file.seek(10)  # Move cursor to the 10th byte
    print(file.read())  # Read from that position
```

---

### **`tell()` - Get Current Cursor Position**
```python
with open("example.txt", "r") as file:
    print(file.tell())  # Shows cursor position
    file.read(5)  
    print(file.tell())  # Shows updated position
```

---

### **`truncate(size)` - Resize File**  
If `size` is provided, it trims the file; otherwise, it truncates from the current position.
```python
with open("example.txt", "w") as file:
    file.write("Hello, World!")
    file.truncate(5)  # File now contains "Hello"
```

---

## **6. Checking If a File Exists Before Deleting**
```python
import os
if os.path.exists("example.txt"):
    os.remove("example.txt")
else:
    print("File does not exist")
```

---

## **7. Handling File Exceptions**  
```python
try:
    with open("example.txt", "r") as file:
        print(file.read())
except FileNotFoundError:
    print("File not found!")
except IOError:
    print("Error reading/writing file")
```

---

## **Why Use File Handling?**  
1. **Data Persistence** – Store data permanently.  
2. **Data Sharing** – Share text, images, and logs.  
3. **Logging & Debugging** – Store logs for error tracking.  
4. **Large Data Processing** – Work with big datasets efficiently.  
5. **Control Over File Positioning** – Read/write from any position using `seek()`, `tell()`, and `truncate()`.  

---

### **📌 Summary**
- `open("file", "mode")` to open a file.  
- Modes: `"r"`, `"w"`, `"a"`, `"x"`, `"rb"`, `"wb"`.  
- Always use `with open()` to avoid manual closing.  
- `seek(offset, whence)`, `tell()`, and `truncate(size)` control file positioning.  
- Handle errors using `try-except`.  
- Use `os.remove()` to delete files safely.  

This **covers ALL essential file handling concepts**, including advanced methods like `seek()` and `truncate()`. 🚀  
