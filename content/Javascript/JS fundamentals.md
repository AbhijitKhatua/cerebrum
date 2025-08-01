JavaScript is a cross-platform, object-oriented scripting language used to make webpages interactive (e.g., having complex animations, clickable buttons, popup menus, etc.). There are also more advanced server side versions of JavaScript such as Node.js, which allow you to add more functionality to a website than downloading files (such as realtime collaboration between multiple computers). Inside a host environment (for example, a web browser), JavaScript can be connected to the objects of its environment to provide programmatic control over them.

JavaScript contains a standard library of objects, such as `Array`, `Map`, and `Math`, and a core set of language elements such as operators, control structures, and statements. Core JavaScript can be extended for a variety of purposes by supplementing it with additional objects; for example:

- _Client-side JavaScript_ extends the core language by supplying objects to control a browser and its _Document Object Model_ (DOM). For example, client-side extensions allow an application to place elements on an HTML form and respond to user events such as mouse clicks, form input, and page navigation.
- _Server-side JavaScript_ extends the core language by supplying objects relevant to running JavaScript on a server. For example, server-side extensions allow an application to communicate with a database, provide continuity of information from one invocation to another of the application, or perform file manipulations on a server.

This means that in the browser, JavaScript can change the way the webpage (DOM) looks. And, likewise, Node.js JavaScript on the server can respond to custom requests sent by code executed in the browser.

### JavaScript Vs Java

No class, no type, no access modifier. Very flexible.
```js
function add(a, b) {
  return a + b;
}

x = 5; // No declaration. Works, but sloppy and unsafe.
```

Declare a class. Define access modifiers (`public`, etc.) Specify types for everything.
```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
}

int x = 5; // must declare type
```

JavaScript didn’t have private or protected access modifiers until **ES2020**, which introduced `#privateFields` in classes.

```js
class Example {
  #secret = 42; // truly private
}
```

JavaScript is **not statically typed**, and there is no concept of interfaces baked into the language.

But you might use **TypeScript** or **JSDoc** to enforce similar interface contracts:

```ts
interface Person {
  name: string;
  age: number;
}
```

```java
interface Person {
  String getName();
  int getAge();
}
```

Java:

- Compiles to bytecode → runs on JVM → fast, optimized.
- Is **statically typed**, which allows compile-time checks and optimizations.
- Ensures you don’t do illegal memory operations (can’t cast `int` to `Object` directly, etc.).

**JavaScript**, being dynamic:

- Has less optimization potential.
- Detects errors at runtime (e.g., accessing `undefined.length` crashes the app).
- Is more prone to runtime bugs without tooling (e.g., TypeScript or linters).

#### Inheritance
```java
class Animal {}
class Dog extends Animal {}
```

Java encourages class hierarchies
This often leads to deep inheritance chains, which are **rigid** and can become tightly coupled.

But modern Java now encourages composition over inheritance, with patterns like interfaces, dependency injection, etc.

JavaScript is **prototype-based**, not class-based (at least originally). You can simulate inheritance via:

```js
function Animal() {}
Animal.prototype.speak = () => console.log("speak");

function Dog() {}
Dog.prototype = Object.create(Animal.prototype);
```

in ES6+ Syntactic Sugar

```js
class Animal {}
class Dog extends Animal {}
```
So while JavaScript looks class-based now, under the hood it’s **still prototype-based** — and more flexible.

---

JavaScript borrows most of its syntax from Java, C, and C++, but it has also been influenced by Awk, Perl, and Python.

JavaScript is **case-sensitive** and uses the **Unicode** character set. For example, the word Früh (which means "early" in German) could be used as a variable name.

```
const Früh = "foobar";
```

But, the variable `früh` is not the same as `Früh` because JavaScript is case sensitive.

In JavaScript, instructions are called [statements](https://developer.mozilla.org/en-US/docs/Glossary/Statement) and are separated by semicolons (;).

A semicolon is not necessary after a statement if it is written on its own line. But if more than one statement on a line is desired, then they _must_ be separated by semicolons.

[^1]
[^1]: **Note:** ECMAScript also has rules for automatic insertion of semicolons ([ASI](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#automatic_semicolon_insertion)) to end statements. (For more information, see the detailed reference about JavaScript's [lexical grammar](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar).)

**The source text of JavaScript script gets scanned from left to right, and is converted into a sequence of input elements which are _tokens_, _control characters_, _line terminators_, _comments_, or [whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace). (Spaces, tabs, and newline characters are considered whitespace.)**

## [Comments](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#comments)

The syntax of **comments** is the same as in C++ and in many other languages:

```js
// a one line comment

/* this is a longer,
 * multi-line comment
 */
```

You can't nest block comments. This often happens when you accidentally include a `*/` sequence in your comment, which will terminate the comment.

```js
/* You can't, however, /* nest comments */ SyntaxError */
```

In this case, you need to break up the `*/` pattern. For example, by inserting a backslash:

```js
/* You can /* nest comments *\/ by escaping slashes */
```

## [Declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#declarations)

JavaScript has three kinds of variable declarations.

[`var`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)

Declares a variable, optionally initializing it to a value.

[`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)

Declares a block-scoped, local variable, optionally initializing it to a value.

[`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)

Declares a block-scoped, read-only named constant.

### [Variables](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#variables)

You use variables as symbolic names for values in your application. The names of variables, called [identifiers](https://developer.mozilla.org/en-US/docs/Glossary/Identifier), conform to certain rules.

A JavaScript identifier usually starts with a letter, underscore (`_`), or dollar sign (`$`). Subsequent characters can also be digits (`0` – `9`). Because JavaScript is case sensitive, letters include the characters `A` through `Z` (uppercase) as well as `a` through `z` (lowercase).

You can use most Unicode letters such as `å` and `ü` in identifiers. (For more details, see the [lexical grammar](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#identifiers) reference.) You can also use [Unicode escape sequences](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#string_literals) to represent characters in identifiers.

Some examples of legal names are `Number_hits`, `temp99`, `$credit`, and `_name`.

### [Declaring variables](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#declaring_variables)

You can declare a variable in two ways:

- With the keyword [`var`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var). For example, `var x = 42`. This syntax can be used to declare both **local** and **global** variables, depending on the _execution context_.
- With the keyword [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) or [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let). For example, `let y = 13`. This syntax can be used to declare a block-scope local variable. (See [Variable scope](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#variable_scope) below.)

You can declare variables to unpack values using the [destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring) syntax. For example, `const { bar } = foo`. This will create a variable named `bar` and assign to it the value corresponding to the key of the same name from our object `foo`.

Variables should always be declared before they are used. JavaScript used to allow assigning to undeclared variables, which creates an **[undeclared global](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var#description)** variable. This is an error in [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode#assigning_to_undeclared_variables) and should be avoided altogether.

### [Declaration and initialization](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#declaration_and_initialization)

In a statement like `let x = 42`, the `let x` part is called a _declaration_, and the `= 42` part is called an _initializer_. The declaration allows the variable to be accessed later in code without throwing a [`ReferenceError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError), while the initializer assigns a value to the variable. In `var` and `let` declarations, the initializer is optional. If a variable is declared without an initializer, it is assigned the value [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

```js
let x;
console.log(x); // logs "undefined"
```

In essence, `let x = 42` is equivalent to `let x; x = 42`.

`const` declarations always need an initializer, because they forbid any kind of assignment after declaration, and implicitly initializing it with `undefined` is likely a programmer mistake.

```js
const x; // SyntaxError: Missing initializer in const declaration
```

```js
const x = undefined;
```

### [Variable scope](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#variable_scope)

A variable may belong to one of the following [scopes](https://developer.mozilla.org/en-US/docs/Glossary/Scope):

- Global scope: The default scope for all code running in script mode.
- Module scope: The scope for code running in module mode.
- Function scope: The scope created with a [function](https://developer.mozilla.org/en-US/docs/Glossary/Function).

In addition, variables declared with [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let) or [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) can belong to an additional scope:

- Block scope: The scope created with a pair of curly braces (a [block](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block)).

When you declare a variable outside of any function, it is called a _global_ variable, because it is available to any other code in the current document. When you declare a variable within a function, it is called a _local_ variable, because it is available only within that function.

`let` and `const` declarations can also be scoped to the [block statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling#block_statement) that they are declared in.

```js
if (Math.random() > 0.5) {
  const y = 5;
}
console.log(y); // ReferenceError: y is not defined
```

However, variables created with `var` are not block-scoped, but only local to the _function (or global scope)_ that the block resides within.

For example, the following code will log `5`, because the scope of `x` is the global context (or the function context if the code is part of a function). The scope of `x` is not limited to the immediate `if` statement block.

```js
if (true) {
  var x = 5;
}
console.log(x); // x is 5
```

### [Variable hoisting](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#variable_hoisting)

`var`-declared variables are [hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting), meaning you can refer to the variable anywhere in its scope, even if its declaration isn't reached yet. You can see `var` declarations as being "lifted" to the top of its function or global scope. However, if you access a variable before it's declared, the value is always `undefined`, because only its _declaration_ and _default initialization (with `undefined`)_ is hoisted, but not its _value assignment_.

```js
console.log(x === undefined); // true
var x = 3;

(function () {
  console.log(x); // undefined
  var x = "local value";
})();
```

The above examples will be interpreted the same as:

```js
var x;
console.log(x === undefined); // true
x = 3;

(function () {
  var x;
  console.log(x); // undefined
  x = "local value";
})();
```

Because of hoisting, all `var` statements in a function should be placed as near to the top of the function as possible. This best practice increases the clarity of the code.

Whether `let` and `const` are hoisted is a matter of definition debate. Referencing the variable in the block before the variable declaration always results in a [`ReferenceError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError), because the variable is in a "[temporal dead zone](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#temporal_dead_zone_tdz)" from the start of the block until the declaration is processed.

```js
console.log(x); // ReferenceError
const x = 3;

console.log(y); // ReferenceError
let y = 3;
```

Unlike `var` declarations, which only hoist the declaration but not its value, [function declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#function_hoisting) are hoisted entirely — you can safely call the function anywhere in its scope. See the [hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) glossary entry for more discussion.

### [Global variables](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#global_variables)

Global variables are in fact properties of the _global object_.
In JavaScript, the **global object** is a special object that holds all global variables and functions.
- **In browsers**, the global object is `window`.
- **In modern environments** (browser, Node.js, etc.), there's also `globalThis` for cross-environment compatibility.

> 📌 So any variable declared globally with `var` becomes a property of `window` (or `globalThis`):

```js
var x = 10;
console.log(window.x); // 10
console.log(globalThis.x); // 10
```

```js
let y = 20;
console.log(window.y); // undefined
```

When you use `<iframe>` or open a new browser window with `window.open()`, each one gets its own **execution context** and **global object**.

But… JavaScript allows you to access those contexts from each other _as long as they're on the same origin (same domain, protocol, and port)_.

```html
`<!-- main.html --> <iframe name="myFrame" src="child.html"></iframe> <script>   var phoneNumber = "123-456-7890"; </script>`
```

In `child.html`, you can do:

```js
`console.log(parent.phoneNumber); // Accesses the variable from main.html`
```

Or from the parent window:

```js
`console.log(frames['myFrame']); // Reference to the iframe window`
```

### [Constants](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#constants)
You can create a read-only, named constant with the [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const) keyword. The syntax of a constant identifier is the same as any variable identifier: it must start with a letter, underscore, or dollar sign (`$`), and can contain alphabetic, numeric, or underscore characters.

```js
const PI = 3.14;
```

A constant cannot change value through assignment or be re-declared while the script is running. It must be initialized to a value. The scope rules for constants are the same as those for `let` block-scope variables.

You cannot declare a constant with the same name as a function or variable in the same scope. For example:

```js
// THIS WILL CAUSE AN ERROR
function f() {}
const f = 5;

// THIS WILL CAUSE AN ERROR TOO
function f() {
  const g = 5;
  var g;
}
```

However, `const` only prevents _re-assignments_, but doesn't prevent _mutations_. The properties of objects assigned to constants are not protected, so the following statement is executed without problems.

```js
const MY_OBJECT = { key: "value" };
MY_OBJECT.key = "otherValue";
```

Also, the contents of an array are not protected, so the following statement is executed without problems.

```js
const MY_ARRAY = ["HTML", "CSS"];
MY_ARRAY.push("JAVASCRIPT");
console.log(MY_ARRAY); // ['HTML', 'CSS', 'JAVASCRIPT'];
```

### [[Data Structures & Types In JavaScript]]

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