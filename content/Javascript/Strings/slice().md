This method extracts a portion of a string and returns a new string, without modifying the original string. It takes two parameters: the starting index and the optional ending index.

```js
const text = "freeCodeCamp";
console.log(text.slice(0,4)); // "free"
console.log(text.slice(4,8)); // "Code"
console.log(text.slice(8,13)); // "Camp"
```

If you omit the second parameter, `slice()` will extract everything from the start index to the end of the string:

```js
let message = "Hello, world!";
let world = message.slice(7);

console.log(world);  // Output: world!
```
You can also use negative numbers as indexes. When you use a negative number, it counts backward from the end of the string:

```js
let message = "JavaScript is fun!";
let lastWord = message.slice(-4);

console.log(lastWord);  // Output: fun!
```

In this case, `slice(-4)` extracts the last four characters from the string, giving us `fun!`.

```js
let sentence = "Learning JavaScript is fun!";
let extracted = sentence.slice(9, -5);

console.log(extracted); // Output: JavaScript is
