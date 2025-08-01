The `push()` method is used to add one or more elements to the end of an array. The return value for the `push()` method is the new length of the array. Here's an example of adding a new fruit to the existing `fruits` array:

```js
const fruits = ["apple", "banana"];
const newLength = fruits.push("orange");
console.log(newLength); // 3
console.log(fruits); // ["apple", "banana", "orange"]
```

In this example, we start with an array called `fruits` which contains two elements. We then use the `push()` method to add the string `orange` to the end of the array.

You might have noticed that we are using `const` when declaring the `fruits` array. But why is it possible to add more elements to this `fruits` array when `fruits` is a constant? This is possible because declaring an array with the `const` keyword creates a reference to the array. While the array itself is mutable and can be modified, you cannot reassign a new value to the `fruits` constant, like this:

```js
const fruits = ["apple", "banana"];
fruits = ["This", "will", "not", "work"];
console.log(fruits); // Uncaught TypeError: Assignment to constant variable. 
```
