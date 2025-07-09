While HTML and CSS provide website structure, JavaScript brings interactivity to websites by enabling complex functionality, such as handling user input, animating elements, and even building full web applications.

## [[JS fundamentals]]

### Data Types

Data types help the program understand the kind of data it's working with, whether it's a number, text, or something else.

- [[Number Type]]: A number represents both integers and floating-point values. Examples of integers include 7, 19, and 90.
- **Floating point**: A floating point number is a number with a decimal point. Examples include 3.14, 0.5, and 0.0001.
- **String**: A string is a sequence of characters, or text, enclosed in quotes. `"I like coding"` and `'JavaScript is fun'` are examples of strings.
- [[Booleans]]: A boolean represents one of two possible values: `true` or `false`. You can use a boolean to represent a condition, such as `isLoggedin = true`.
- [[Undefined & Null]]: An `undefined` value is a variable that has been declared but not assigned a value. A `null` value is an empty value, or a variable that has intentionally been assigned a value of `null`.
- **Object**: An object is a collection of key-value pairs. The key is the property name, and the value is the property value.
- **Symbol**: The Symbol data type is a unique and immutable value that may be used as an identifier for object properties.

```js
const crypticKey1= Symbol("saltNpepper");
const crypticKey2= Symbol("saltNpepper");
console.log(crypticKey1 === crypticKey2); // false
```

- **BigInt**: When the number is too large for the `Number` data type, you can use the BigInt data type to represent integers of arbitrary length. By adding an `n` to the end of the number, you can create a BigInt.

```js
const veryBigNumber = 1234567890123456789012345678901234567890n;
```
### Variables In JS

1. [[Var]], Let & const
2. To assign a value to a variable, you can use the assignment operator `=`.
3. Variables declared using `let` can be reassigned a new value.
4. Apart from `let`, you can also use `const` to declare a variable. However, a `const` variable cannot be reassigned a new value.
### [[String]]

- Strings are sequences of characters enclosed in quotes. They can be created using single quotes and double quotes.
- Strings are immutable in JavaScript. This means that once a string is created, you cannot change the characters in the string. However, you can still reassign strings to a new value.
### String Concatenation in JavaScript

- Concatenation is the process of joining multiple strings or combining strings with variables that hold text. The `+` operator is one of the simplest and most frequently used methods to concatenate strings.

```js
let studentName = "Asad";
let studentAge = 25;
let studentInfo = studentName + " is " + studentAge + " years old.";
console.log(studentInfo); // Asad is 25 years old.
```

- If you need to add or append to an existing string, then you can use the `+=` operator. This is helpful when you want to build upon a string by adding more text to it over time.
- Another way you can concatenate strings is to use the `concat()` method. This method joins two or more strings together.

```js
let firstName = "John";
let lastName = "Doe";
let fullName = firstName.concat(" ", lastName);
console.log(fullName); // John Doe
```

### Logging Messages with `console.log()`

- The `console.log()` method is used to log messages to the console. It's a helpful tool for debugging and testing your code.
### JavaScript as a Dynamically Typed Language

- JavaScript is a dynamically typed language, which means that you don't have to specify the data type of a variable when you declare it. The JavaScript engine automatically determines the data type based on the value assigned to the variable.

```js
let error = 404; // JavaScript treats error as a number
error = "Not Found"; // JavaScript now treats error as a string
```

### Using the `typeof` Operator

- The `typeof` operator is used to check the data type of a variable. It returns a string indicating the type of the variable.

```js
let age = 25;
console.log(typeof age); // "number"

let isLoggedin = true;
console.log(typeof isLoggedin); // "boolean"
```

- However, there's a well-known quirk in JavaScript when it comes to `null`. The `typeof` operator returns `"object"` for `null` values.

```js
let user = null;
console.log(typeof user); // "object"
```

### [[Functions]]

In JavaScript, functions and object methods are both ways to encapsulate reusable code, but they have some key differences in how they are defined, used, and the context in which they operate. Understanding these differences is crucial for writing effective and organized JavaScript code.
 [[Difference Between Functions and Object Methods]]
### [[Operators]]

### [[Statements]]

### [[Methods]]

### [[Objects]]

In JavaScript, understanding the difference between [[primitive and non-primitive data types]] is important for writing efficient and bug-free code.
### [[Arrays]]

## [[Loops]]
## [[Constructors]]
[[Common Practices for Naming Variables and Functions]]

### [[ Linters and Formatters]]
### [[ Memory Management]]

### [[Closures]]

### [[Modules]]
[[Async JS]]
[[Fetch API]]
[[Promise]]
[[Engine & Runtime]]

### [[Geolocation API]]
[[CRUD]]

[[OOPs]]
[[Maps & Sets]]

---------------------
### What Is [[JSON]], and How Do You Access Values Using Bracket and Dot Notation?


---

### Fundamental Object

| Name       | Description                                     |
| ---------- | ----------------------------------------------- |
| `Object`   | Base of all objects.                            |
| `Function` | Base function object.                           |
| `Boolean`  | Boolean wrapper object.                         |
| `Symbol`   | Unique and immutable value used as object keys. |
### Global Value Properties
|Name|Description|
|---|---|
|`globalThis`|The global `this` value across environments.|
|`Infinity`|Represents mathematical infinity.|
|`NaN`|Not a Number value.|
|`undefined`|Primitive value used when a variable is not assigned.|

### Global Function Properties
|Name|Description|
|---|---|
|`eval()`|Evaluates JavaScript code represented as a string.|
|`isFinite()`|Checks if a value is a finite number.|
|`isNaN()`|Checks if a value is `NaN`.|
|`parseFloat()`|Parses a string to a floating point number.|
|`parseInt()`|Parses a string to an integer.|
|`decodeURI()`|Decodes a full URI.|
|`decodeURIComponent()`|Decodes a URI component.|
|`encodeURI()`|Encodes a full URI.|
|`encodeURIComponent()`|Encodes a URI component.|
|`escape()` (Deprecated)|Encodes a string. Deprecated.|
|`unescape()` (Deprecated)|Decodes an encoded string. Deprecated.|

### Numbers and Dates
|Name|Description|
|---|---|
|`Number`|Represents numbers.|
|`BigInt`|Arbitrary precision integers.|
|`Math`|Math constants and functions.|
|`Date`|Dates and times.|
|`Temporal`|Modern date/time API (proposal stage).|

### Error Objects
|Name|Description|
|---|---|
|`Error`|Base error object.|
|`AggregateError`|Represents multiple errors.|
|`EvalError`|Error in `eval()`.|
|`RangeError`|Number out of allowable range.|
|`ReferenceError`|Invalid reference to a variable.|
|`SyntaxError`|Incorrect syntax.|
|`TypeError`|Incorrect type usage.|
|`URIError`|Error in URI handling.|
|`InternalError`|Non-standard internal error.|
### Text Processing
| Name     | Description          |
| -------- | -------------------- |
| `String` | String manipulation. |
| `RegExp` | Regular expressions. |

### Indexed Collections

|Name|Description|
|---|---|
|`Array`|Indexed collection of values.|
|`TypedArray`|Generic typed array base.|
|`Int8Array`|8-bit signed integer array.|
|`Uint8Array`|8-bit unsigned integer array.|
|`Uint8ClampedArray`|8-bit unsigned clamped array.|
|`Int16Array`|16-bit signed integer array.|
|`Uint16Array`|16-bit unsigned integer array.|
|`Int32Array`|32-bit signed integer array.|
|`Uint32Array`|32-bit unsigned integer array.|
|`BigInt64Array`|64-bit signed BigInt array.|
|`BigUint64Array`|64-bit unsigned BigInt array.|
|`Float16Array`|16-bit float array.|
|`Float32Array`|32-bit float array.|
|`Float64Array`|64-bit float array.|

### Keyed Collections
|Name|Description|
|---|---|
|`Map`|Key-value pairs; remembers insertion order.|
|`Set`|Unique values; remembers insertion order.|
|`WeakMap`|Keys are weakly held.|
|`WeakSet`|Values are weakly held.|

### Structured Data
|Name|Description|
|---|---|
|`ArrayBuffer`|Raw binary data buffer.|
|`SharedArrayBuffer`|Shared buffer for threading.|
|`DataView`|Low-level interface to buffer data.|
|`Atomics`|Atomic operations for shared memory.|
|`JSON`|JSON parsing and stringifying.|

### Managing Memory
|Name|Description|
|---|---|
|`WeakRef`|Weak reference to an object.|
|`FinalizationRegistry`|Cleanup logic when object is GC’d.|

### Control Abstractions

|Name|Description|
|---|---|
|`Iterator`|Protocol for iteration.|
|`AsyncIterator`|Async version of Iterator.|
|`Promise`|Represents a future value.|
|`GeneratorFunction`|Function that yields values.|
|`AsyncGeneratorFunction`|Async generator function.|
|`Generator`|Iterator returned from generator.|
|`AsyncGenerator`|Async version of generator.|
|`AsyncFunction`|Function using `async` keyword.|

### Reflection 
|Name|Description|
|---|---|
|`Reflect`|Provides methods for interceptable operations.|
|`Proxy`|Custom behavior for fundamental operations.|

### Internationalization (Intl)
|Name|Description|
|---|---|
|`Intl`|Namespace for i18n features.|
|`Intl.Collator`|String comparison.|
|`Intl.DateTimeFormat`|Date and time formatting.|
|`Intl.DisplayNames`|Localized display names.|
|`Intl.DurationFormat`|Formatting durations (proposal).|
|`Intl.ListFormat`|Formatting lists.|
|`Intl.Locale`|BCP 47 language tag parsing.|
|`Intl.NumberFormat`|Number formatting.|
|`Intl.PluralRules`|Rules for pluralization.|
|`Intl.RelativeTimeFormat`|Relative time formatting (e.g., "2 days ago").|
|`Intl.Segmenter`|Unicode text segmentation.|
