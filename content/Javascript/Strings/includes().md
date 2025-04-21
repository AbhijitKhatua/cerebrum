This method is used to check if a string contains a specific substring. If the substring is found within the string, the method returns true. Otherwise, it returns false.
its a case sensitive method
```js
const text = "The quick brown fox jumps over the lazy dog.";
console.log(text.includes("fox")); // true
console.log(text.includes("cat")); // false
```

You can also use the `includes()` method to check for a substring starting at a specific index in the string by providing a second parameter:

Example Code

```js
let text = "Hello, JavaScript world!";
let result = text.includes("JavaScript", 7);

console.log(result);  // true
```

Here, the search for the substring JavaScript starts from the 7th position in the string, ensuring it skips any characters before this position.The includes() method only returns a true or false result. It does not provide information on where the substring is located in the string or how many times it occurs. If you need that level of detail, other methods, such as the indexOf() method might be more suitable.