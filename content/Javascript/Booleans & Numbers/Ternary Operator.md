The ternary operator is a compact way to write simple `if/else` statements. It has three parts: a condition, a result if the condition is true, and a result if it is false. Here's the basic syntax:

```js
condition ? expressionIfTrue : expressionIfFalse;
```

Here's an example dealing with weather temperatures in Celsius:

```js
const weather = temperature > 25 ? 'sunny' : 'cool';

console.log(`It's a ${weather} day!`);
```

If `temperature` is greater than `25`, the code above logs `It's a sunny day!`. If `temperature` is ever less than `25`, it logs `It's a cool day!`.

So, which should you use between an if statement and a ternary? Use a ternary while dealing with a single condition or single expressions, or when you want a compact syntax for simple logic. Use `if/else` statements when you're dealing with complex conditions and multiple statements, as things become unreadable if you nest ternaries.