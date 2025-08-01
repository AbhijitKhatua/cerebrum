In JavaScript, an object is a fundamental data structure that allows you to store and organize related data and functionality.

You can think of an object as a container that holds various pieces of information, much like a filing cabinet holds different folders and documents.

These pieces of information are called properties, and they consist of a name (or key) and a value.

```js
const exampleObject = {
  propertyName: value;
}
```

Objects are incredibly versatile and form the backbone of JavaScript. In fact, almost everything in JavaScript is an object or can be treated as one. This includes arrays, functions, and even primitive data types like strings and numbers when used in certain ways.

This object-centric nature of JavaScript is one of the reasons it's such a flexible and powerful language. Let's look at how you can create an object:

```js
const person = {
  name: "Alice",
  age: 30,
  city: "New York"
};
```

In this example, we've created an object calle\d `person` with three properties: `name`, `age`, and `city`. Each property has a name and a value, separated by a colon.

Now, let's explore how you can access these properties. There are two main ways to access object properties in JavaScript: dot notation and bracket notation.

Dot notation is the most common and straightforward way to access object properties. Here is the basic syntax for dot notation.

```js
objectName.propertyName
```

Here's how you would use dot notation with our `person` object:

```js
const person = {
  name: "Alice",
  age: 30,
  city: "New York"
};

console.log(person.name);  // Alice
console.log(person.age);   // 30
```

Dot notation is concise and easy to read, making it the preferred choice when you know the exact name of the property you want to access and that name is a valid JavaScript identifier (meaning it doesn't start with a number and doesn't contain special characters or spaces).

Bracket notation, on the other hand, allows you to access object properties using a string inside square brackets. Here's how you would use bracket notation:

```js
const person = {
  name: "Alice",
  age: 30,
  city: "New York"
};

console.log(person["name"]); // Alice
console.log(person["age"]); //  30
```

Bracket notation is more flexible than dot notation because it allows you to use property names that aren't valid JavaScript identifiers. For example, if you had a property name with spaces or that starts with a number, you'd need to use bracket notation:

```js
const oddObject = {
  "1stProperty": "Hello",
  "property with spaces": "World"
};

console.log(oddObject["1stProperty"]);  // Hello
console.log(oddObject["property with spaces"]);  // World
```

Another advantage of bracket notation is that it allows you to use variables to access properties dynamically.

```js
const person = {
  name: "Alice",
  age: 30,
  city: "Wonderland"
};

let propertyName = "city";
console.log(person[propertyName]); // Wonderland
```

This flexibility makes bracket notation particularly useful when you don't know the exact property name at the time you're writing the code, or when you're working with property names that come from user input or some other dynamic source.

It's worth noting that objects in JavaScript are incredibly powerful and versatile. They can contain not just simple values like strings and numbers, but also arrays, or other objects.

Understanding objects and how to work with them is crucial in JavaScript because they're used extensively throughout the language and in many JavaScript libraries and frameworks.

As you continue to learn and work with JavaScript, you'll find that mastering objects opens up a world of possibilities for creating complex and powerful applications.

[[Object Destructuring]]

There are several ways to remove properties from an object, with the `delete` operator being the most straightforward and commonly used method.

When you use `delete`, it removes the selected property from the object. Here's an example of how to use the [[delete operator]].

In JavaScript, there are several ways to check if an object has a specific property. Understanding these methods is important for working effectively with objects, especially when you're dealing with data from external sources or when you need to ensure certain properties exist before using them.

We'll explore three common approaches: the [[hasOwnProperty()]] method, the `in` operator, and checking against `undefined`.

When working with JavaScript, you'll often encounter complex data structures that involve [[nested objects and arrays]] within objects. These structures can represent rich, hierarchical data, but they also require a clear understanding of how to access and manipulate the data within them. Let's explore how to navigate these nested structures effectively.

In JavaScript, understanding the difference between [[primitive and non-primitive data types]] is important for writing efficient and bug-free code.

In JavaScript, a [[constructor]] is a special type of function used to create and initialize objects. It is invoked with the `new` keyword and can initialize properties and methods on the newly created object.

what is [[optional chaining operator]]

In JavaScript, almost "everything" is an object.

- Objects are objects
- Maths are objects
- Functions are objects
- Dates are objects
- Arrays are objects
- Maps are objects
- Sets are objects

All JavaScript values, except primitives, are objects.

---

## JavaScript Primitives

A **primitive value** is a value that has no properties or methods.

**3.14** is a primitive value

A **primitive data type** is data that has a primitive value.

JavaScript defines 7 types of primitive data types:

- `string`
- `number`
- `boolean`
- `null`
- `undefined`
- `symbol`
- `bigint`

Objects written as name value pairs are similar to:

- Associative arrays in PHP
- Dictionaries in Python
- Hash tables in C
- Hash maps in Java
- Hashes in Ruby and Perl



----------------------------------------
- [[Math Object]]
- 