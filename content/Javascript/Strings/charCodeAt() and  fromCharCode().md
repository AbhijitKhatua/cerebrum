
- **ASCII**: ASCII, short for American Standard Code for Information Interchange, is a character encoding standard used in computers to represent text. It assigns a numeric value to each character, which is universally recognized by machines.
- **The `charCodeAt()` Method**: This method is called on a string and returns the ASCII code of the character at a specified index.

```js
const letter = "A";
console.log(letter.charCodeAt(0));  // 65
```

- **The `fromCharCode()` Method**: This method converts an ASCII code into its corresponding character.

```js
const char = String.fromCharCode(65);
console.log(char);  // A