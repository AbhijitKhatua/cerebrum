```javascript
1. IndexOf()
2. charCodeAt()
3. includes()
4. slice()
5. toUpperCase()
6. toLowerCase()
7. replace()
8. repeat()
9. trim()
10. trimStart()
11. trimEnd()
12. prompt()
```

- **The `indexOf` Method**: This method is used to search for a substring within a string. If the substring is found, `indexOf` returns the index (or position) of the first occurrence of that substring. If the substring is not found, `indexOf` returns -1, which indicates that the search was unsuccessful.

```js
const text = "The quick brown fox jumps over the lazy dog.";
console.log(text.indexOf("fox")); // 16
console.log(text.indexOf("cat")); // -1
```

- **The `includes()` Method**: This method is used to check if a string contains a specific substring. If the substring is found within the string, the method returns true. Otherwise, it returns false.
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

- **The  [[slice()]] Method**: This method extracts a portion of a string and returns a new string, without modifying the original string. It takes two parameters: the starting index and the optional ending index.

- **The [[toUpperCase() & toLoweCase()]] Method**: 

```js
const text = "Hello, world!";
console.log(text.toUpperCase()); // "HELLO, WORLD!"
```

```js
const text = "HELLO, WORLD!"
console.log(text.toLowerCase()); // "hello, world!"
```

- **The [[replace()]] Method**: This method is used to find a specified value (like a word or character) in a string and replace it with another value.

```js
const text = "I like cats";
console.log(text.replace("cats", "dogs")); // "I like dogs"
```

- **The [[repeat()]] Method**: This method is used to repeat a string a specified number of times.

```js
const text = "Hello";
console.log(text.repeat(3)); // "HelloHelloHello"
```

- **The [[trim()]] Method**: This method is used to remove whitespaces from both the beginning and the end of a string.

```js
const text = "  Hello, world!  ";
console.log(text.trim()); // "Hello, world!"
```

- **The `trimStart()` Method**: This method removes whitespaces from the beginning (or "start") of the string.

```js
const text = "  Hello, world!  ";
console.log(text.trimStart()); // "Hello, world!  "
```

- **The `trimEnd()` Method**: This method removes whitespaces from the end of the string.

```js
const text = " Hello, world! ";
console.log(text.trimEnd()); // "  Hello, world!"
```

- The [[prompt()]] Method 1: This method of the `window` is used to get information from a user through the form of a dialog box. This method takes two arguments. The first argument is the message which will appear inside the dialog box, typically prompting the user to enter information. The second one is a default value which is optional and will fill the input field initially.

```js
const answer = window.prompt("What's your favorite animal?"); // This will change depend
```

