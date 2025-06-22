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
### OOP Principles: Inheritance

Inheritance is one of the foundations of object-oriented programming.

In essence, it's a very simple concept. It works like this:

1. There is a base class of a "thing".
    
2. There are one or more sub-classes of "things" that inherit the properties of the base class (sometimes also referred to as the "super-class")
    
3. There might be some other sub-sub-classes of "things" that inherit from those classes in point 2.
    

Note that each sub-class inherits from its super-class. In turn, a sub-class might also be a super-class, if there are classes inheriting from that sub-class.

Here's a practical example:

1. There is a base class of Animal.
    
2. There is another class, a sub-class inheriting from Animal, and the name of this class is Mammal.
    
3. Next, there is another class, inheriting from Mammal, and this class is Elephant.
    

Thus, in the above example, I'm modeling objects from the real world by constructing relationships between Animal, Mammal, and Elephant. Each of them is a separate class, a blueprint for specific object instances that can be constructed as needed.

To set up the inheritance relation between classes in JavaScript, I can use the extends keyword, as in: 

class B extends A.

Here's an example of an inheritance hierarchy in JavaScript:

```javascript
class Animal { /* ...class code here... */ };

class Mammal extends Animal { /* ...class code here... */ };

class Elephant extends Mammal { /* ...class code here... */ };
```

### OOP Principles: Encapsulation

In the simplest terms, encapsulation has to do with making a code implementation "hidden" from other users, in the sense that they don't have to know how my code works in order to "consume" the code.

For example, when I run the following code:

```javascript
"abc".toUpperCase();
```

I don't really need to worry or even waste time thinking about how the toUpperCase() method works. All I want is to use it, since I know it's available to me. Even if the underlying syntax - that is, the implementation of the toUpperCase() method changes - as long as it doesn't break my code, I don't have to worry about what it does in the background, or even how it does it.

### OOP Principles: Abstraction

Abstraction is all about writing code in a way that will make it more generalized.

The concepts of encapsulation and abstraction are often misunderstood because their differences can feel blurry.

It helps to think of it in the following terms:

- Abstraction is about extracting the _concept_ of what you're trying to do, rather than dealing with a specific manifestation of that concept.
    
- Encapsulation is about you not having access to, or not being concerned with, how some implementation works internally.
    

While both the encapsulation and abstraction are important concepts in OOP, it requires more experience with programming in general to fully grasp these topics.

For now, it's enough to be aware of their existence in OOP.

### OOP Principles: Polymorphism

Polymorphism is a word derived from the Greek language meaning "multiple forms". An alternative translation might be "something that can take on many shapes."

So, to understand what polymorphism is about, let's consider some real-life objects.

- A door has a bell. It could be said that the bell is a property of the door object. This bell can be rung. When would someone ring a bell on the door? Obviously, to get someone to show up at the door.
    
- Now consider a bell on a bicycle. A bicycle has a bell. It could be said that the bell is a property of the bicycle object. This bell could also be rung. However, the reason, the intention, and the result of somebody ringing the bell on a bicycle is not the same as ringing the bell on a door.
    

The above concepts can be coded in JavaScript as follows:

```javascript
const bicycle = {

    bell: function() {

        return "Ring, ring! Watch out, please!";

    }

}

const door = {

    bell: function() {

        return "Ring, ring! Come here, please!";

    }

}
```

You can access the bell() method on each object like this:

```javascript
bicycle.bell(); // "Ring, ring! Watch out, please!"
door.bell();    // "Ring, ring! Come here, please!"
```

At this point, one can conclude that the exact same name of the method can have the exact opposite intent, based on what object it is used for.

Now, to make this code truly polymorphic, I will add another function declaration:

```javascript
function ringTheBell(thing) {
    console.log(thing.bell());
}
```

Now I have declared a ringTheBell() function. It accepts a thing parameter - which I expect to be an object, namely, either the bicycle object or the door object.

Now, you can invoke ringTheBell() with either object:

```javascript
ringTheBell(bicycle); // Ring, ring! Watch out, please!
ringTheBell(door); // "Ring, ring! Come here, please!"
```

You've now seen an example of the exact same function producing different results, **based on the context** in which it is used. Polymorphism is useful because it allows developers to build objects that can share functionality but override it as needed.

Another example of polymorphism is the concatenation operator, used by calling the built-in concat() method.

If I use the concat() method on two strings, it behaves exactly the same as if I used the + operator.

```javascript
"abc".concat("def"); // 'abcdef'
```

I can also use the concat() method on two arrays. Here's the result:

```javascript
["abc"].concat(["def"]); // ['abc', 'def']
```

Consider using the + operator on two arrays with one member each:

```javascript
["abc"] + ["def"]; // "abc,def"
```

This means that the concat() method is exhibiting polymorphic behavior since it behaves differently based on the context - in this case, based on what data types I give it. However, take a note that using the + operator with arrays does not perform true concatenation. Instead, it coerces the arrays into strings before joining them and elements are separated by commas.

This behavior is different from the concat() method, which preserves the array structure.

To reiterate, polymorphism is useful because it allows developers to build objects that can have the exact same functionality, or functions with the exact same name which behave exactly the same. However, at the same time, you can override some parts of the shared functionality or even the complete functionality, in some other parts of the OOP structure.

Here's an example of polymorphism using classes in JavaScript:

```js
class Bird {
    useWings() {
        console.log("Flying!");
    }
}

class Eagle extends Bird {
    useWings() {
        super.useWings();
        console.log("Barely flapping!");
    }
}

class Penguin extends Bird {
    useWings() 
        console.log("Diving!");
    }
}

var baldEagle = new Eagle();
var kingPenguin = new Penguin();
baldEagle.useWings(); // "Flying! Barely flapping!"
kingPenguin.useWings(); // "Diving!"
```

The super keyword calls methods from the parent class. In the Eagle class, super.useWings() invokes the useWings() method from the Bird class, allowing the Eagle class to extend its behavior by adding "Barely flapping!" after calling the parent method.

The Penguin and Eagle sub-classes both inherit from the Bird super-class.

The Eagle sub-class inherits the useWings() method from the Bird class, but extends it with an additional console log. The Penguin sub-class doesn't inherit the useWings() method - instead, it has its own implementation, although the Penguin class itself does extend the Bird class.

Using the skeleton of the code above, try creating some of your own classes. (hint: think about things you know from everyday life, like your house.)

```js
// create your classes here
```

Object-oriented programming (OOP) simplifies code by modeling real-world relationships through principles like inheritance, encapsulation, abstraction, and polymorphism. These principles promote modular, reusable, and flexible code, making software easier to extend and maintain.
