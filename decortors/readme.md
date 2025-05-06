 ### Decorator in Python
A decorator is like a wrapper that modifies or extends a function's behavior without changing its actual code.





# logging_decorator.py

def log_decorator(func):
    def wrapper(*args, **kwargs):
        print(f"[LOG] Calling function: {func.__name__}")
        print(f"[LOG] Arguments: {args}, Keyword Arguments: {kwargs}")
        result = func(*args, **kwargs)
        print(f"[LOG] {func.__name__} returned: {result}")
        return result
    return wrapper

@log_decorator
def add(a, b):
    return a + b

@log_decorator
def greet(name):
    return f"Hello, {name}!"

# Example usage
add(3, 4)
greet("Alisha")





documentation:
https://www.geeksforgeeks.org/decorators-in-python/
