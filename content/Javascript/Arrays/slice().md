Another method to create a shallow copy is the `slice()` method. When called without arguments, `slice()` returns a shallow copy of the entire array. Here's how it works

```js
let originalArray = [1, 2, 3];
let copyArray = originalArray.slice();

console.log(copyArray); // [1, 2, 3]
console.log(copyArray === originalArray); // false
```

In this case, `originalArray.slice()` creates a new array that is a shallow copy of `originalArray`. Again, the `copyArray` contains the same elements but is a different array object.

