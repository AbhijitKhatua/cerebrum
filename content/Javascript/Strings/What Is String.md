- **Definition**: A string is a sequence of characters wrapped in either single quotes, double quotes or backticks. Strings are primitive data types and they are immutable. Immutability means that once a string is created, is cannot be changed.
- **Accessing Characters from a String**: To access a character from a string you can use bracket notation and pass in the index number. An index is the position of a character within a string, and it is zero-based.

```js
const developer = "Jessica";
developer[0] // J
```

- **`\n` (Newline Character)**: You can create a newline in a string by using the `\n` newline character.

```js
const poem = "Roses are red,\nViolets are blue,\nJavaScript is fun,\nAnd so are you.";
console.log(poem);
```

- **Escaping Strings**: You can escape characters in a string by placing backlashes (`\`) in front of the quotes.

```js
const statement = "She said, \"Hello!\"";
console.log(statement); // She said, "Hello!"
```

## Other Common [[String Methods]]
