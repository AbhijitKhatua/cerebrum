What is the `Object()` constructor and when should you use it?

In this video, we will take a look at how to work with the `Object()` constructor. The `Object()` constructor creates a new empty object. Here is an example:

```js
new Object()
```

When you call `new Object()`, it returns a new object that can be used to store values.

The `Object()` constructor can be used with or without the `new` keyword. When called as a function without `new`, it behaves differently depending on the type of value passed to it. Here's an example of using the `Object()` constructor without the `new` keyword:

```js
const num = 42;
const numObj = Object(num); // Creates an object wrapper for the number

console.log(numObj); // 42
console.log(typeof numObj); // "object"
```

The first `console.log` will show `42`, but it is important to note that this is not a regular number. As you can see in the second `console.log`, `numObj` is an object. This is happening because we used the `Object()` constructor to turn that input of a number into an object.

What happens if we try to pass `null` or `undefined` to the `Object()` constructor?

```js
const newObj = new Object(undefined);
console.log(newObj); // {}
```

Well, the result will be an empty object. Another use case for the `Object()` constructor is when you're working with a value of unknown type and you need to ensure it's an object. Let’s take a look at the following example:

```js
function toObject(value) {
  if (value === null || value === undefined) {
    return {};
  }

  if (typeof value === "object") {
    return value;
  }

  return Object(value);
}

console.log(toObject(null));

console.log(toObject(true));

console.log(toObject([1, 2, 3]));
```

In this example, we have a function called `toObject`. The second condition will check if the value is a type of object and will return the value if the condition is `true`. This condition will check for objects as well as arrays since arrays are special types of objects.

If neither of the conditions is true, the function returns `Object(value)`, which converts the input into an object. This works for values like numbers, strings, and booleans

Most of the time you will not be using the `Object()` constructor to create new objects because you will be using object literal syntax instead (e.g., `const objectLiteral = { name: "Beau" }`). But it is still good to understand the basics of working with the Object constructor.