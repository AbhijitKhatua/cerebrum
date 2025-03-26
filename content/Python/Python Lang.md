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

## Built-in Data Types

In programming, data type is an important concept.

Variables can store data of different types, and different types can do different things.

Python has the following data types built-in by default, in these categories:

|                 |                                    |
| --------------- | ---------------------------------- |
| Text Type:      | `str`                              |
| Numeric Types:  | `int`, `float`, `complex`          |
| Sequence Types: | `list`, `tuple`, `range`           |
| Mapping Type:   | `dict`                             |
| Set Types:      | `set`, `frozenset`                 |
| Boolean Type:   | `bool`                             |
| Binary Types:   | `bytes`, `bytearray`, `memoryview` |
| None Type:      | `NoneType`                         |
```python
x = 5  
print(type(x))
```

|Example|Data Type|Try it|
|---|---|---|
|x = "Hello World"|str|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_str)|
|x = 20|int|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_int)|
|x = 20.5|float|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_float)|
|x = 1j|complex|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_complex)|
|x = ["apple", "banana", "cherry"]|list|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_list)|
|x = ("apple", "banana", "cherry")|tuple|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_tuple)|
|x = range(6)|range|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_range)|
|x = {"name" : "John", "age" : 36}|dict|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_dict)|
|x = {"apple", "banana", "cherry"}|set|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_set)|
|x = frozenset({"apple", "banana", "cherry"})|frozenset|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_frozenset)|
|x = True|bool|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_bool)|
|x = b"Hello"|bytes|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_bytes)|
|x = bytearray(5)|bytearray|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_bytearray)|
|x = memoryview(bytes(5))|memoryview|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_memoryview)|
|x = None|NoneType|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_nonetype)|


## Setting the Specific Data Type

If you want to specify the data type, you can use the following constructor functions:

|Example|Data Type|Try it|
|---|---|---|
|x = str("Hello World")|str|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_str2)|
|x = int(20)|int|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_int2)|
|x = float(20.5)|float|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_float2)|
|x = complex(1j)|complex|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_complex2)|
|x = list(("apple", "banana", "cherry"))|list|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_list2)|
|x = tuple(("apple", "banana", "cherry"))|tuple|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_tuple2)|
|x = range(6)|range|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_range2)|
|x = dict(name="John", age=36)|dict|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_dict2)|
|x = set(("apple", "banana", "cherry"))|set|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_set2)|
|x = frozenset(("apple", "banana", "cherry"))|frozenset|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_frozenset2)|
|x = bool(5)|bool|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_bool2)|
|x = bytes(5)|bytes|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_bytes2)|
|x = bytearray(5)|bytearray|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_bytearray2)|
|x = memoryview(bytes(5))|memoryview|[Try it »](https://www.w3schools.com/python/trypython.asp?filename=demo_type_memoryview2)|

---
## Python Numbers

There are three numeric types in Python:

- `int`
- `float`
- `complex`

```python
x = 1    # int  
y = 2.8  # float  
z = 1j   # complex
```

Integer
```python
x = 1  
y = 35656222554887711  
z = -3255522  
```

float
```python
x = 1.10  
y = 1.0  
z = -35.59
```

Float can also be scientific numbers with an "e" to indicate the power of 10.
```python
x = 35e3  
y = 12E4  
z = -87.7e100
```

## Complex

Complex numbers are written with a "j" as the imaginary part:

```python
x = 3+5j  
y = 5j  
z = -5j
```

## Type Conversion

You can convert from one type to another with the `int()`, `float()`, and `complex()` methods:

```python
x = 1    # int  
y = 2.8  # float  
z = 1j   # complex  
  
#convert from int to float:  
a = float(x)  
  
#convert from float to int:  
b = int(y)  
  
#convert from int to complex:  
c = complex(x)
```

## Random Number

Python does not have a `random()` function to make a random number, but Python has a built-in module called `random` that can be used to make random numbers:

```python
import random  
  
print(random.randrange(1, 10))
```
