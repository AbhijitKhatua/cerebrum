In this section, you will learn:

1. What constructors are and how they work in JavaScript.
2. How to use built-in constructors like Date and Math.
3. How to define and use custom constructor functions.
4. When to use object literals instead of constructors for better performance.

By the end, you’ll understand the key concepts of constructors and how to apply them effectively.

JavaScript has a number of built-in object types, such as:

 `Math`, `Date`, `Object`, `Function`, `Boolean`, `Symbol`, `Array`, `Map`, `Set`, `Promise`, `JSON`, and many more.

These objects are commonly known as "native objects."

### **Using Constructor Functions**

Constructor functions, commonly referred to as just "constructors", are special functions that allow us to build instances of these built-in native objects. All the constructor functions are capitalized.

To use a constructor function, I must prepend it with the operator new.

For example, to create a new instance of the Date object, I can run: new Date(). What I get back is the current date and time, such as:

Thu Feb 03 2022 11:24:08 GMT+0100 (Central European Standard Time)

However, not all the built-in objects come with a constructor function. An example of such an object type is the built-in Math object.

### **Objects Without Constructors**

Running new Math() throws an Uncaught TypeError, informing us that Math is not a constructor.

Thus, I can conclude that some built-in objects do not have constructors, when they serve a particular purpose: to allow us to instantiate a specific instance of a given object's constructor. The built-in Date object is perfectly suited for having a constructor because each new date object instance I build should have unique data by definition, since it's going to be a different timestamp - it's going to be built at a different moment in time.

Other built-in objects that don't have constructors, such as the Math object, don't need a constructor. They're just static objects whose properties and methods can be accessed directly, from the built-in object itself. In other words, there is no point in building an instance of the built-in Math object to be able to use its functionality.

For example, if I want to use the pow method of the Math object to calculate exponential values, there's no need to build an instance of the Math object to do so. To illustrate, to get the number 2 to the power of 5, I'd run:

`Math.pow(2,5); // --> 32`

There's no need to build an instance of the Math object since nothing needs to be stored in that specific object's instance.

Besides constructor functions for the built-in objects, I can also define custom constructor functions.

### **Custom Constructor Functions**

Let us first look at an example:

```javascript
function Icecream(flavor) {

    this.flavor = flavor;

    this.meltIt = function() {

        console.log(`The ${this.flavor} icecream has melted`);

    }

}
```


Now I can make as many ice creams as I want:

```javascript
function Icecream(flavor) {

    this.flavor = flavor;

    this.meltIt = function() {

        console.log(`The ${this.flavor} icecream has melted`);

    }

}

let kiwiIcecream = new Icecream("kiwi");

let appleIcecream = new Icecream("apple");

kiwiIcecream; // --> Icecream {flavor: 'kiwi', meltIt: ƒ}

appleIcecream; // --> Icecream {flavor: 'apple', meltIt: ƒ}

```


I've just built two instance objects of Icecream type.

The most common use case of new is to use it with one of the built-in object types.

### **Performance and Best Practices with Constructors**

Note that using constructor functions on all built-in objects is sometimes not the best approach.

This is especially true for object constructors of primitive types, namely: String, Number, and Boolean.

For example, using the built-in String constructor, I can build new strings:

```javascript
let apple = new String("apple");

apple; // --> String {"apple"}
```

The apple variable is an object of type String.

Let's see how the apple object differs from the following pear variable:

```javascript
let pear = "pear";

pear; // --> "pear"
```

The pear variable is a string literal, that is, a primitive JavaScript value.

The pear variable, being a primitive value, will always be more performant than the apple variable, which is an object.

Besides being more performant, due to the fact that each object in JavaScript is unique, you can't compare a String object with another String object, even when their values are identical.

In other words, if you compare new String('plum') === new String('plum'), you'll get back false, while "plum" === "plum" returns true. You're getting the false when comparing objects because it is not the values that you pass to the constructor that are being compared, but rather the memory location where objects are saved.

Besides not using constructors to build object versions of primitives, you are better off not using constructors when constructing plain, regular objects.

### **Alternative Patterns and Literals**

Instead of new Object, you should stick to the object literal syntax: `{}`.

A `RegExp` object is another built-in object in JavaScript. It's used to **pattern-match strings** using what's known as "Regular Expressions". Regular Expressions exist in many languages, not just JavaScript.

In JavaScript, you can build an instance of the `RegExp` constructor using new `RegExp()`.

Alternatively, you can use a pattern literal instead of `RegExp`. Here's an example of using /d/ as a pattern literal, passed-in as an argument to the match method on a string.

```javascript
"abcd".match(/d/); // ['d', index: 3, input: 'abcd', groups: undefined]

"abcd".match(/a/); // ['a', index: 0, input: 'abcd', groups: undefined]
```

Instead of using Array, Function, and `RegExp` constructors, you should use their array literal, function literal, and pattern literal varieties: `[]`, `()` `{},` and `/()/`.

However, when building objects of other built-in types, we can use the constructor.

Here are a few examples:
```javascript
new Date();
new Error();
new Map();
new Promise();
new Set();
new WeakSet();
new WeakMap();
```

The above list is not exhaustive, but it's just there to give you an idea of some constructor functions you can surely use.

Note that there are links provided about RegExp and regular expression in the lesson item titled _"Additional Reading"_.

Understanding constructors in JavaScript is crucial for building efficient and flexible code. By mastering both built-in and custom constructors, you'll be able to create dynamic objects tailored to your needs, improve performance, and follow best practices. This knowledge will enhance your ability to write clean, maintainable code, making you a more proficient JavaScript developer.


- [[Number()]]
- [[Audio constructer]]