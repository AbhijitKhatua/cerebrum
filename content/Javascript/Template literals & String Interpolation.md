When Used backticks instead oof single or double quote to represent a string its called template literals it serves the purpose string manipulation(Inserting variables and expressions directly into a string) using JS the process is called string interpolation 

```javascript
let name = 'Alice';
let greeting = `Hello, ${name}!`;
```

Another great feature of template literals is that they support multiline strings. With regular strings, you would need to use escape characters (`\n`) to create new lines. With template literals, you can simply write the string across multiple lines, and the formatting is preserved:

```js
let poem = `Roses are red,
Violets are blue,
JavaScript is fun,
And so are you.`;

console.log(poem);
```

The output will retain the line breaks as written:

```md
Roses are red,
Violets are blue,
JavaScript is fun,
And so are you.
```