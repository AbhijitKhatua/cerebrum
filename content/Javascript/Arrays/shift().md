the `shift()` method removes the first element from an array and returns that element. It's similar to `pop()`, but it works at the beginning of the array instead of the end. Here's how it works:

```js
let colors = ["red", "green", "blue"];
let firstColor = colors.shift();
console.log(colors); // ["green", "blue"]
console.log(firstColor); // "red"
```

In this example, we start with an array of three colors. The `shift()` method removes the first element (`red`) from the array and returns it. The original `colors` array is modified to contain only two elements.

*Note that while `push()` and `unshift()` can add multiple elements at once, `pop()` and `shift()` remove only one element at a time.*