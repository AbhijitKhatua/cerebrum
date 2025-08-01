The `unshift()` method adds one or more elements to the beginning of an array and returns its new length. It works similarly to `push()`, but modifies the start of the array instead of the end. Here's an example:

```js
let numbers = [2, 3];
let newLength = numbers.unshift(1);
console.log(numbers); // [1, 2, 3]
console.log(newLength); // 3
```

In this example, we use `unshift()` to add the number `1` to the beginning of the `numbers` array. The method returns the new length of the array, which is `3`.

