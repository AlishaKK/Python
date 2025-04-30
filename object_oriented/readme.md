

---

# Python Object-Oriented Programming (OOP) Concepts

This repository demonstrates key **Object-Oriented Programming (OOP)** principles in Python. The aim is to help you learn and master fundamental OOP concepts, including **Encapsulation**, **Inheritance**, **Polymorphism**, **Abstraction**, and **Access Modifiers**.

Each concept is explained with clear examples, showcasing their usage and benefits in real-world Python projects.

---

## Table of Contents

- [Introduction](#introduction)
- [Key OOP Concepts](#key-oop-concepts)
  - [Class & Object](#class--object)
  - [Encapsulation](#encapsulation)
  - [Inheritance](#inheritance)
  - [Polymorphism](#polymorphism)
  - [Abstraction](#abstraction)
  - [Access Modifiers](#access-modifiers)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Introduction

**Object-Oriented Programming (OOP)** is a paradigm that models real-world entities as **objects**, containing both data and behaviors. This approach is widely used in modern software development, as it provides a clean, maintainable, and scalable way to organize code.

In this repository, you’ll find code examples that demonstrate the following OOP concepts in Python:

- **Class & Object**
- **Encapsulation**
- **Inheritance**
- **Polymorphism**
- **Abstraction**
- **Access Modifiers**

---

## Key OOP Concepts

### 1. Class & Object
- A **class** is a blueprint for creating objects (instances).
- An **object** is an instance of a class that can hold data and execute methods.

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def display_info(self):
        print(f"Car Brand: {self.brand}, Model: {self.model}")

# Creating an object (instance)
car = Car("Toyota", "Corolla")
car.display_info()  # Output: Car Brand: Toyota, Model: Corolla
```

---

### 2. Encapsulation
- **Encapsulation** refers to hiding the internal state of an object and only exposing a controlled interface. This is done by making attributes **private** and using **getter** and **setter** methods to access them.

```python
class BankAccount:
    def __init__(self, initial_balance):
        self.__balance = initial_balance  # Private attribute

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
        else:
            print("Invalid deposit amount.")

    def get_balance(self):
        return self.__balance

account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())  # Output: 1500
```

---

### 3. Inheritance
- **Inheritance** allows a class (child class) to inherit properties and methods from another class (parent class). It promotes **code reuse**.

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def speak(self):
        print("Dog barks")

dog = Dog()
dog.speak()  # Output: Dog barks
```

---

### 4. Polymorphism
- **Polymorphism** allows a method to behave differently based on the object that is calling it. The same method name can perform different actions depending on the class of the object.

```python
class Dog:
    def speak(self):
        print("Dog barks")

class Cat:
    def speak(self):
        print("Cat meows")

def animal_speak(animal):
    animal.speak()

dog = Dog()
cat = Cat()
animal_speak(dog)  # Output: Dog barks
animal_speak(cat)  # Output: Cat meows
```

---

### 5. Abstraction
- **Abstraction** hides the complex implementation details and shows only the essential features of an object. It is often achieved using **abstract classes** and **abstract methods**.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * (self.radius ** 2)

circle = Circle(5)
print(circle.area())  # Output: 78.5
```

---

### 6. Access Modifiers
Python uses a convention to indicate the visibility of class attributes and methods:

- **Public**: Accessible from anywhere (`self.attribute`)
- **Protected**: Meant to be accessed within the class and subclass (convention: `self._attribute`)
- **Private**: Restricted access, only within the class (convention: `self.__attribute`)

```python
class MyClass:
    def __init__(self):
        self.public = "I am public"
        self._protected = "I am protected"
        self.__private = "I am private"

obj = MyClass()
print(obj.public)       # Accessible
print(obj._protected)   # Accessible (but not recommended)
print(obj.__private)    # Not accessible directly
```

---


