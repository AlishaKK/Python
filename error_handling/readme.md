

---

### **What is Error Handling in Python?**  
Error handling is the process of catching and managing errors that may occur during program execution. In Python, we use the `try`, `except`, `else`, and `finally` blocks to handle errors gracefully instead of letting the program crash.

---

### **1. Basic Try-Except Block**  
**Definition:** The `try` block contains the code that may cause an error, and the `except` block catches and handles the error.  

```python
try:
    num = int(input("Enter a number: "))  # This may cause a ValueError if input is not a number
    print("You entered:", num)
except ValueError:  # This block handles the ValueError
    print("Oops! That's not a valid number.")
```
🔹 **If the user enters a number**, it will print the number.  
🔹 **If the user enters text (e.g., "hello")**, it will print the error message.

---

### **2. Handling Multiple Exceptions**  
**Definition:** You can use multiple `except` blocks to handle different types of errors separately.  

```python
try:
    num1 = int(input("Enter first number: "))
    num2 = int(input("Enter second number: "))
    result = num1 / num2  # This may cause ZeroDivisionError
    print("Result:", result)
except ZeroDivisionError:  # Catches division by zero error
    print("Error: Cannot divide by zero!")
except ValueError:  # Catches input conversion error
    print("Error: Please enter only numbers.")
```
🔹 **If the user enters valid numbers**, it prints the result.  
🔹 **If they enter 0 as the second number**, it shows a `ZeroDivisionError` message.  
🔹 **If they enter text instead of a number**, it shows a `ValueError` message.

---

### **3. Using Else and Finally**  
**Definition:**  
- The `else` block runs only when no exception occurs.  
- The `finally` block runs **always**, whether an exception occurs or not (useful for resource cleanup).  

```python
try:
    file = open("example.txt", "r")  # Trying to open a file
    content = file.read()
    print(content)
except FileNotFoundError:  # Catches error if file doesn't exist
    print("Error: File not found.")
else:
    print("File read successfully.")  # Runs only if no error occurs
finally:
    print("Closing file...")
    file.close()  # Ensures file is closed no matter what
```
🔹 **If the file exists**, it reads the content and prints "File read successfully."  
🔹 **If the file doesn't exist**, it prints "Error: File not found."  
🔹 **The `finally` block runs no matter what**, ensuring that the file is closed.

---

### **4. Raising Custom Exceptions**  
**Definition:** The `raise` keyword allows you to manually trigger an exception when a specific condition is met.  

```python
def check_age(age):
    if age < 18:
        raise ValueError("You must be 18 or older.")  # Manually raising an exception
    else:
        print("Access granted.")

try:
    user_age = int(input("Enter your age: "))
    check_age(user_age)
except ValueError as e:  # Catching the custom exception
    print("Error:", e)
```
🔹 **If the user enters 18 or more**, it prints "Access granted."  
🔹 **If they enter a number less than 18**, it raises an error saying, "You must be 18 or older."

---

### **💡 Key Takeaways:**  
✔ `try`: Runs the code that might cause an error.  
✔ `except`: Catches and handles errors.  
✔ `else`: Runs if no error occurs.  
✔ `finally`: Runs **always**, for cleanup tasks.  
✔ `raise`: Manually triggers exceptions.  


