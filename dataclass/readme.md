
 structured progression of `dataclass` examples, categorized into **Beginner**, **Intermediate**, and **Advanced** levels. Each section includes a "Before" (without `dataclass`) and "After" (with `dataclass`) comparison to highlight the benefits of using `dataclass`.

---

## **🔰 Beginner Level**
### **Before (Without `dataclass`)**
```python
class User:
    def __init__(self, username, email, age):
        self.username = username
        self.email = email
        self.age = age

    def __repr__(self):
        return f"User(username={self.username}, email={self.email}, age={self.age})"

# Instance
user = User("alisha_kayani", "alisha@example.com", 23)
print(user)
```

### **After (With `dataclass`)**
```python
from dataclasses import dataclass

@dataclass
class User:
    username: str
    email: str
    age: int

# Instance
user = User("alisha_kayani", "alisha@example.com", 23)
print(user)
```
**✅ Benefits:**
- Less boilerplate code (no need for `__init__` or `__repr__` methods)
- Readable and cleaner structure

---

## **🚀 Intermediate Level**
### **Before (Without `dataclass`)**
```python
class Book:
    def __init__(self, title, author, year, price, is_ebook=False):
        self.title = title
        self.author = author
        self.year = year
        self.price = price
        self.is_ebook = is_ebook

    def __repr__(self):
        return (f"Book(title={self.title}, author={self.author}, "
                f"year={self.year}, price={self.price}, is_ebook={self.is_ebook})")

# Instance
book = Book("Python Crash Course", "Eric Matthes", 2019, 29.99, is_ebook=True)
print(book)
```

### **After (With `dataclass`)**
```python
from dataclasses import dataclass

@dataclass
class Book:
    title: str
    author: str
    year: int
    price: float
    is_ebook: bool = False  # Default value

# Instance
book = Book("Python Crash Course", "Eric Matthes", 2019, 29.99, is_ebook=True)
print(book)
```
**✅ Benefits:**
- Default values (`is_ebook=False`)
- Improved readability and maintainability

---

## **🔥 Advanced Level**
### **Before (Without `dataclass`)**
```python
class Employee:
    def __init__(self, id, name, department, salary, is_full_time=True):
        self.id = id
        self.name = name
        self.department = department
        self.salary = salary
        self.is_full_time = is_full_time

    def __repr__(self):
        return (f"Employee(id={self.id}, name={self.name}, "
                f"department={self.department}, salary={self.salary}, is_full_time={self.is_full_time})")

    def yearly_bonus(self):
        return self.salary * 0.1  # 10% bonus

# Instance
employee = Employee(101, "Alice Johnson", "Engineering", 75000.00)
print(employee)
print(f"Yearly Bonus: ${employee.yearly_bonus():.2f}")
```

### **After (With `dataclass`)**
```python
from dataclasses import dataclass

@dataclass
class Employee:
    id: int
    name: str
    department: str
    salary: float
    is_full_time: bool = True

    def yearly_bonus(self) -> float:
        return self.salary * 0.1  # 10% bonus

# Instance
employee = Employee(101, "Alice Johnson", "Engineering", 75000.00)
print(employee)
print(f"Yearly Bonus: ${employee.yearly_bonus():.2f}")
```
**✅ Benefits:**
- Method inside `dataclass` (`yearly_bonus`)
- Type hints for better code clarity

---

### **💎 Expert-Level Bonus: Frozen and Order**
```python
from dataclasses import dataclass

@dataclass(frozen=True, order=True)
class Car:
    brand: str
    model: str
    year: int
    price: float

# Instances
car1 = Car("Tesla", "Model 3", 2023, 50000)
car2 = Car("BMW", "X5", 2022, 60000)

# Comparison (enabled by `order=True`)
print(car1 < car2)  # True (compares based on fields)
```
**✅ Benefits:**
- `frozen=True`: Makes objects immutable (cannot be modified after creation)
- `order=True`: Enables sorting and comparisons (`<`, `>`, etc.)

---

## **🔚 Summary**
| Level         | Features Introduced |
|--------------|-------------------|
| **Beginner**  | Basic `dataclass`, removes `__init__`, `__repr__` |
| **Intermediate** | Default values, improved maintainability |
| **Advanced** | Methods inside `dataclass`, enhanced structure |
| **Expert** | `frozen=True` (immutability), `order=True` (sorting & comparison) |
