print("Hello, World!")

```python
#This is a comment  
print("Hello, World!")
```

```python
"""  
This is a comment  
written in  
more than just one line  
"""  
print("Hello, World!")
```

Python has no command for declaring a variable.

A variable is created the moment you first assign a value to it.

```python
x = 5  
y = "John"  
print(x)  
print(y)
```

```python
x = 4       # x is of type int  
x = "Sally" # x is now of type str  
print(x)
```

```python
x = str(3)    # x will be '3'  
y = int(3)    # y will be 3  
z = float(3)  # z will be 3.0
```

A variable can have a short name (like x and y) or a more descriptive name (age, carname, total_volume).

Rules for Python variables:

- A variable name must start with a letter or the underscore character
- A variable name cannot start with a number
- A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
- Variable names are case-sensitive (age, Age and AGE are three different variables)
- A variable name cannot be any of the [Python keywords](https://www.w3schools.com/python/python_ref_keywords.asp).

```python
myvar = "John"  
my_var = "John"  
_my_var = "John"  
myVar = "John"  
MYVAR = "John"  
myvar2 = "John"
```


```python
x, y, z = "Orange", "Banana", "Cherry"  
print(x)  
print(y)  
print(z)
```

```python
x = y = z = "Orange"  
print(x)  
print(y)  
print(z)
```

```python
fruits = ["apple", "banana", "cherry"]  
x, y, z = fruits  
print(x)  
print(y)  
print(z)
```

```python
x = "Python is awesome"  
print(x)
```

```python
x = "Python"  
y = "is"  
z = "awesome"  
print(x, y, z)
```

```python
x = "Python "  
y = "is "  
z = "awesome"  
print(x + y + z)
```

```python
x = 5  
y = 10  
print(x + y)
```


#### Function
```python
x = "awesome"  
  
def myfunc():  
  print("Python is " + x)  
  
myfunc()
```

```python
x = "awesome"  
  
def myfunc():  
  x = "fantastic"  
  print("Python is " + x)  
  
myfunc()  
  
print("Python is " + x)
```

Normally, when you create a variable inside a function, that variable is local, and can only be used inside that function.

To create a global variable inside a function, you can use the `global` keyword.

```python
def myfunc():  
  global x  
  x = "fantastic"  
  
myfunc()  
  
print("Python is " + x)
```

```python
x = "awesome"  
  
def myfunc():  
  global x  
  x = "fantastic"  
  
myfunc()  
  
print("Python is " + x)
```

