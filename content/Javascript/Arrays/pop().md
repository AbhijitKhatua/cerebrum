The next method we will look at is the `pop()` method. The `pop()` method removes the last element from an array and returns that element. It also modifies the original array. Here's how it works:

```js
let fruits = ["apple", "banana", "orange"];
let lastFruit = fruits.pop();
console.log(fruits); // ["apple", "banana"]
console.log(lastFruit); // "orange"
```

In this example, we start with an array of three fruits. The `pop()` method removes the last element (`orange`) from the array and returns it. The original `fruits` array is modified and contains only two elements.

*Note that while `push()` and `unshift()` can add multiple elements at once, `pop()` and `shift()` remove only one element at a time.*