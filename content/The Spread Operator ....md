The spread operator (`...`), introduced in ES6, provides another concise way to create shallow copies of arrays. Here's an example:

```js
let originalArray = [1, 2, 3];
let copyArray = [...originalArray];

console.log(copyArray); // [1, 2, 3]
console.log(copyArray === originalArray); // false
```

The spread operator (`...`) spreads the elements of `originalArray` into a new array, effectively creating a shallow copy. It's important to note that all these methods create new array objects, which means you can modify the copy without affecting the original array. For example:

```js
let originalArray = [1, 2, 3];
let copyArray = [...originalArray];

copyArray.push(4);
console.log(originalArray); // [1, 2, 3]
console.log(copyArray);     // [1, 2, 3, 4]
```

In this example, adding an element to `copyArray` doesn't affect `originalArray`.

In summary, shallow copies of arrays can be easily created using methods like `concat()`, `slice()`, or the spread operator. These methods are useful for creating new arrays that can be manipulated independently of the original array.

