### [Data types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#data_types)

The latest ECMAScript standard defines eight data types:

- Seven data types that are [primitives](https://developer.mozilla.org/en-US/docs/Glossary/Primitive):
    
    1. [Boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean). `true` and `false`.
    2. [null](https://developer.mozilla.org/en-US/docs/Glossary/Null). A special keyword denoting a null value. (Because JavaScript is case-sensitive, `null` is not the same as `Null`, `NULL`, or any other variant.)
    3. [undefined](https://developer.mozilla.org/en-US/docs/Glossary/Undefined). A top-level property whose value is not defined.
    4. [Number](https://developer.mozilla.org/en-US/docs/Glossary/Number). An integer or floating point number. For example: `42` or `3.14159`.
    5. [BigInt](https://developer.mozilla.org/en-US/docs/Glossary/BigInt). An integer with arbitrary precision. For example: `9007199254740992n`.
    6. [String](https://developer.mozilla.org/en-US/docs/Glossary/String). A sequence of characters that represent a text value. For example: `"Howdy"`.
    7. [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol). A data type whose instances are unique and immutable.
- and [Object](https://developer.mozilla.org/en-US/docs/Glossary/Object)
    

Although these data types are relatively few, they enable you to perform useful operations with your applications. [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions) are the other fundamental elements of the language. While functions are technically a kind of object, you can think of objects as named containers for values, and functions as procedures that your script can perform.

### [Data type conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#data_type_conversion)

JavaScript is a _dynamically typed_ language. This means you don't have to specify the data type of a variable when you declare it. It also means that data types are automatically converted as-needed during script execution.

So, for example, you could define a variable as follows:

```js
let answer = 42;
```

And later, you could assign the same variable a string value, for example:

```js
answer = "Thanks for all the fish!";
```

Because JavaScript is dynamically typed, this assignment does not cause an error message.

### [Numbers and the '+' operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#numbers_and_the_operator)

In expressions involving numeric and string values with the `+` operator, JavaScript converts numeric values to strings. For example, consider the following statements:

```js
x = "The answer is " + 42; // "The answer is 42"
y = 42 + " is the answer"; // "42 is the answer"
z = "37" + 7; // "377"
```

With all other operators, JavaScript does _not_ convert numeric values to strings. For example:

```js
"37" - 7; // 30
"37" * 7; // 259
```

### [Converting strings to numbers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#converting_strings_to_numbers)

In the case that a value representing a number is in memory as a string, there are methods for conversion.

- [`parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
- [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
- [`Number()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)

`parseInt` only returns whole numbers, so its use is diminished for decimals.

> [!NOTE] Note
> Additionally, a best practice for `parseInt` is to always include the _radix_ parameter. The radix parameter is used to specify which numerical system is to be used.


```js
parseInt("101", 2); // 5
```

An alternative method of retrieving a number from a string is with the `+` (unary plus) operator. This implicitly performs [number conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#number_coercion), which is the same process as the [`Number()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) function

```js
"1.1" + "1.1"; // '1.11.1'
(+"1.1") + (+"1.1"); // 2.2
// Note: the parentheses are added for clarity, not required.
```

## [Literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#literals)

_Literals_ represent values in JavaScript. These are fixed values—not variables—that you _literally_ provide in your script. This section describes the following types of literals:

- [Array literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#array_literals)
- [Boolean literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#boolean_literals)
- [Numeric literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#numeric_literals)
- [Object literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#object_literals)
- [RegExp literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#regexp_literals)
- [String literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#string_literals)
### [Array literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#array_literals)

An array literal is a list of zero or more expressions, each of which represents an array element, enclosed in square brackets (`[]`). When you create an array using an array literal, it is initialized with the specified values as its elements, and its `length` is set to the number of arguments specified.

The following example creates the `coffees` array with three elements and a `length` of three:

```js
const coffees = ["French Roast", "Colombian", "Kona"];
```

An array literal creates a new array object every time the literal is evaluated. For example, an array defined with a literal in the global scope is created once when the script loads. However, if the array literal is inside a function, a new array is instantiated every time that function is called.

> [!NOTE] Note
> Array literals create `Array` objects. See [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) and [Indexed collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections) for details on `Array` objects.

#### Extra commas in array literals

If you put two commas in a row in an array literal, the array leaves an empty slot for the unspecified element. The following example creates the `fish` array:

```js
const fish = ["Lion", , "Angel"];
```

When you log this array, you will see:

```js
const fish = ["Lion", , "Angel"];
console.log(fish);
// [ 'Lion', <1 empty item>, 'Angel' ]
```

Note that the second item is "empty", which is not exactly the same as the actual `undefined` value. When using array-traversing methods like [`Array.prototype.map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map), empty slots are skipped. However, index-accessing `fish[1]` still returns `undefined`.

If you include a trailing comma at the end of the list of elements, the comma is ignored.

In the following example, the `length` of the array is three. There is no `myList[3]` and `myList[1]` is empty. All other commas in the list indicate a new element.

```js
const myList = ["home", , "school"];
```

In the following example, the `length` of the array is four, and `myList[0]` and `myList[2]` are missing.

```js
const myList = [, "home", , "school"];
```

In the following example, the `length` of the array is four, and `myList[1]` and `myList[3]` are missing. **Only the last comma is ignored.**

```js
const myList = ["home", , "school", ,];
```

> [!NOTE] Note
> [Trailing commas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas) help keep git diffs clean when you have a multi-line array, because appending an item to the end only adds one line, but does not modify the previous line.
> 	
>```js
> 	const myList = [
> 	  "home",
> 	  "school",
> 	+ "hospital",
> 	];
>```

### [Boolean literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#boolean_literals)

The Boolean type has two literal values: `true` and `false`.

> [!NOTE] Note
> Do not confuse the primitive Boolean values `true` and `false` with the true and false values of the [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) object.
> 	
> 	The Boolean object is a wrapper around the primitive Boolean data type. See [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) for more information.

### [Numeric literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#numeric_literals)

JavaScript numeric literals include integer literals in different bases as well as floating-point literals in base-10.

Note that the language specification requires numeric literals to be unsigned. Nevertheless, code fragments like `-123.4` are fine, being interpreted as a unary `-` operator applied to the numeric literal `123.4`.
#### Integer literals

Integer and [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) literals can be written in decimal (base 10), hexadecimal (base 16), octal (base 8) and binary (base 2).

- A _decimal_ integer literal is a sequence of digits without a leading `0` (zero).
- A leading `0` (zero) on an integer literal, or a leading `0o` (or `0O`) indicates it is in _octal_. Octal integer literals can include only the digits `0` – `7`.
- A leading `0x` (or `0X`) indicates a _hexadecimal_ integer literal. Hexadecimal integers can include digits (`0` – `9`) and the letters `a` – `f` and `A` – `F`. (The case of a character does not change its value. Therefore: `0xa` = `0xA` = `10` and `0xf` = `0xF` = `15`.)
- A leading `0b` (or `0B`) indicates a _binary_ integer literal. Binary integer literals can only include the digits `0` and `1`.
- A trailing `n` suffix on an integer literal indicates a [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) literal. The [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt) literal can use any of the above bases. Note that leading-zero octal syntax like `0123n` is not allowed, but `0o123n` is fine.

Some examples of integer literals are:

```js
0, 117, 123456789123456789n             (decimal, base 10)
015, 0001, 0o777777777777n              (octal, base 8)
0x1123, 0x00111, 0x123456789ABCDEFn     (hexadecimal, "hex" or base 16)
0b11, 0b0011, 0b11101001010101010101n   (binary, base 2)
```

For more information, see [Numeric literals in the Lexical grammar reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#numeric_literals).

```js
console.log(018 - 015) //5
```
In **non-strict mode**, JavaScript interprets numbers that start with `0` **as octal (base-8)** — **if** the digits allow it.

- `018` → invalid octal → interpreted as **decimal 18**
- `015` → valid octal → interpreted as **decimal 13**

```js
018 (decimal 18) - 015 (octal 13 → decimal 11) = 18 - 13 = 5
```

``` c++
015 (octal)
= 1×8^1 + 5×8^0
= 1×8 + 5×1
= 8 + 5
= 13 (decimal)
```
#### Floating-point literals

A floating-point literal can have the following parts:

- An unsigned decimal integer,
- A decimal point (`.`),
- A fraction (another decimal number),
- An exponent.

The exponent part is an `e` or `E` followed by an integer, which can be signed (preceded by `+` or `-`). A floating-point literal must have at least one digit, and either a decimal point or `e` (or `E`).

### [Object literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#object_literals)

An object literal is a list of zero or more pairs of property names and associated values of an object, enclosed in curly braces (`{}`).


> [!WARNING] **Warning:**
> Do not use an object literal at the beginning of a statement! This will lead to an error (or not behave as you expect), because the `{` will be interpreted as the beginning of a block.

The following is an example of an object literal. The first element of the `car` object defines a property, `myCar`, and assigns to it a new string, `"Saturn"`; the second element, the `getCar` property, is immediately assigned the result of invoking the function `(carTypes("Honda"))`; the third element, the `special` property, uses an existing variable (`sales`).

```js
const sales = "Toyota";

function carTypes(name) {
  return name === "Honda" ? name : `Sorry, we don't sell ${name}.`;
}

const car = { myCar: "Saturn", getCar: carTypes("Honda"), special: sales };

console.log(car.myCar); // Saturn
console.log(car.getCar); // Honda
console.log(car.special); // Toyota
```

Additionally, you can use a numeric or string literal for the name of a property or nest an object inside another. The following example uses these options.

```js
const car = { manyCars: { a: "Saab", b: "Jeep" }, 7: "Mazda" };

console.log(car.manyCars.b); // Jeep
console.log(car[7]); // Mazda
```

Object property names can be any string, including the empty string. If the property name would not be a valid JavaScript [identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier) or number, it must be enclosed in quotes.

Property names that are not valid identifiers cannot be accessed as a dot (`.`) property.

```js
const unusualPropertyNames = {
  "": "An empty string",
  "!": "Bang!",
};
console.log(unusualPropertyNames.""); // SyntaxError: Unexpected string
console.log(unusualPropertyNames.!); // SyntaxError: Unexpected token !
```

Instead, they must be accessed with the bracket notation (`[]`).

```js
console.log(unusualPropertyNames[""]); // An empty string
console.log(unusualPropertyNames["!"]); // Bang!
```

#### Enhanced Object literals

Object literals support a range of shorthand syntaxes that include setting the prototype at construction, shorthand for `foo: foo` assignments, defining methods, making `super` calls, and computing property names with expressions.

Together, these also bring object literals and class declarations closer together, and allow object-based design to benefit from some of the same conveniences.

```js
const obj = {
  // __proto__
  __proto__: theProtoObj,
  // Shorthand for 'handler: handler'
  handler,
  // Methods
  toString() {
    // Super calls
    return `d ${super.toString()}`;
  },
  // Computed (dynamic) property names
  ["prop_" + (() => 42)()]: 42,
};
```

### [RegExp literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#regexp_literals)

A regex literal (which is defined in detail [later](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions)) is a pattern enclosed between slashes. The following is an example of a regex literal.

```js
const re = /ab+c/;
```

### [String literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#string_literals)

A string literal is zero or more characters enclosed in double (`"`) or single (`'`) quotation marks. A string must be delimited by quotation marks of the same type (that is, either both single quotation marks, or both double quotation marks).

The following are examples of string literals:

```js
'foo'
"bar"
'1234'
'one line \n another line'
"Joyo's cat"
```

You should use string literals unless you specifically need to use a `String` object. See [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) for details on `String` objects.

You can call any of the [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object's methods on a string literal value. JavaScript automatically converts the string literal to a temporary String object, calls the method, then discards the temporary String object. You can also use the `length` property with a string literal:

```js
// Will print the number of symbols in the string including whitespace.
console.log("Joyo's cat".length); // In this case, 10.
```

[Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) are also available. Template literals are enclosed by the back-tick (`` ` ``) ([grave accent](https://en.wikipedia.org/wiki/Grave_accent)) character instead of double or single quotes.

Template literals provide syntactic sugar for constructing strings. (This is similar to string interpolation features in Perl, Python, and more.)

```js
// Basic literal string creation
`In JavaScript '\n' is a line-feed.`;

// Multiline strings
`In JavaScript, template strings can run
 over multiple lines, but double and single
 quoted strings cannot.`;

// String interpolation
const name = "Lev",
  time = "today";
`Hello ${name}, how are you ${time}?`;
```

[Tagged templates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#tagged_templates) are a compact syntax for specifying a template literal along with a call to a "tag" function for parsing it. A tagged template is just a more succinct and semantic way to invoke a function that processes a string and a set of relevant values. The name of the template tag function precedes the template literal — as in the following example, where the template tag function is named `print`. The `print` function will interpolate the arguments and serialize any objects or arrays that may come up, avoiding the pesky `[object Object]`.

``` js
const formatArg = (arg) => {
  if (Array.isArray(arg)) {
    // Print a bulleted list
    return arg.map((part) => `- ${part}`).join("\n");
  }
  if (arg.toString === Object.prototype.toString) {
    // This object will be serialized to "[object Object]".
    // Let's print something nicer.
    return JSON.stringify(arg);
  }
  return arg;
};

const print = (segments, ...args) => {
  // For any well-formed template literal, there will always be N args and
  // (N+1) string segments.
  let message = segments[0];
  segments.slice(1).forEach((segment, index) => {
    message += formatArg(args[index]) + segment;
  });
  console.log(message);
};

const todos = [
  "Learn JavaScript",
  "Learn Web APIs",
  "Set up my website",
  "Profit!",
];

const progress = { javascript: 20, html: 50, css: 10 };

print`I need to do:
${todos}
My current progress is: ${progress}
`;

// I need to do:
// - Learn JavaScript
// - Learn Web APIs
// - Set up my website
// - Profit!
// My current progress is: {"javascript":20,"html":50,"css":10}
```

Since tagged template literals are just sugar of function calls, you can re-write the above as an equivalent function call:

```js
print(["I need to do:\n", "\nMy current progress is: ", "\n"], todos, progress);
```

This may be reminiscent of the `console.log`-style interpolation:

```js
const todos = [
  "Learn JavaScript",
  "Learn Web APIs",
  "Set up my website",
  "Profit!",
];

const progress = { javascript: 20, html: 50, css: 10 };

console.log("I need to do:\n%o\nMy current progress is: %o\n", todos, progress);
```

You can see how the tagged template reads more naturally than a traditional "formatter" function, where the variables and the template itself have to be declared separately.

#### Using special characters in strings

In addition to ordinary characters, you can also include special characters in strings, as shown in the following example.

```js
"one line \n another line";
```

The following table lists the special characters that you can use in JavaScript strings.

|Character|Meaning|
|---|---|
|`\0`|Null Byte|
|`\b`|Backspace|
|`\f`|Form Feed|
|`\n`|New Line|
|`\r`|Carriage Return|
|`\t`|Tab|
|`\v`|Vertical tab|
|`\'`|Apostrophe or single quote|
|`\"`|Double quote|
|`\\`|Backslash character|
|`\XXX`|The character with the Latin-1 encoding specified by up to three octal digits `XXX` between `0` and `377`. For example, `\251` is the octal sequence for the copyright symbol.|
|`\xXX`|The character with the Latin-1 encoding specified by the two hexadecimal digits `XX` between `00` and `FF`. For example, `\xA9` is the hexadecimal sequence for the copyright symbol.|
|`\uXXXX`|The Unicode character specified by the four hexadecimal digits `XXXX`. For example, `\u00A9` is the Unicode sequence for the copyright symbol. See [Unicode escape sequences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#string_literals).|
|`\u{XXXXX}`|Unicode code point escapes. For example, `\u{2F804}` is the same as the Unicode escapes `\uD87E\uDC04`.|
#### Escaping characters

For characters not listed in the table, a preceding backslash is ignored, but this usage is deprecated and should be avoided.

You can insert a quotation mark inside a string by preceding it with a backslash. This is known as _escaping_ the quotation mark. For example:

```js
const quote = "He read \"The Cremation of Sam McGee\" by R.W. Service.";
console.log(quote);
```

The result of this would be:

He read "The Cremation of Sam McGee" by R.W. Service.

To include a literal backslash inside a string, you must escape the backslash character. For example, to assign the file path `c:\temp` to a string, use the following:

```js
const home = "c:\\temp";
```

You can also escape line breaks by preceding them with backslash. The backslash and line break are both removed from the value of the string.

```js
const str =
  "this string \
is broken \
across multiple \
lines.";
console.log(str); // this string is broken across multiple lines.
```

