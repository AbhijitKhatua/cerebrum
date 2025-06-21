In this reading, you'll learn about the benefits of object-oriented programming (OOP) and the OOP principles.

## The Benefits of OOP

There are many benefits to using the object-oriented programming (OOP) paradigm.

OOP helps developers to mimic the relationship between objects in the real world. In a way, it helps you to reason about relationships between things in your software, just like you would in the real world. Thus, OOP is an effective approach to come up with solutions in the code you write. OOP also:

- Allows you to write modular code
    
- Makes your code more flexible
    
- Makes your code reusable.
    

## The Principles of OOP

The four fundamental OOP principles are **inheritance**, **encapsulation**, **abstraction** and **polymorphism**. You'll learn about each of these principles in turn. The thing to remember about Objects is that they exist in a hierarchical structure, meaning that the original base or super class for everything is the **Object** class, and all objects derive from this class. This allows us to utilize the Object.create() method. to create or instantiate objects of our classes.

```javascript
class Animal { /* ...class code here... */ }

var myDog = Object.create(Animal)

console.log (Animal)

RunReset
```


A more common method of creating objects from classes is to use the new keyword. When using a default or empty constructor method, JavaScript implicitly calls the Object superclass to create the instance.

```javascript
class Animal { /* ...class code here... */ }

var myDog = new Animal()

console.log (Animal)

RunReset
```


This concept is explored within the next section on inheritance.