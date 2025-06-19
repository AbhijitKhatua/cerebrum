When diving into JavaScript, you'll quickly discover that performing mathematical operations is a common task. While basic arithmetic operators can handle simple calculations, JavaScript offers a built-in `Math` object to tackle more complex math challenges.

This handy tool provides a variety of methods that make it easier to perform advanced calculations and manipulate numbers. Let's explore these methods and see how they can simplify your coding experience.

The `Math.random()` method generates a random floating-point number between `0` (inclusive) and `1` (exclusive). This means the possible output can be `0`, but it will never actually reach `1`. Here is an example working with the `Math.random()` method:

```js
const randomNum = Math.random();

console.log(randomNum); 
// any number between 0 and 1 – 0 inclusive and 1 exclusive
```

`Math.min()` and `Math.max()` both take a set of numbers and return the minimum and maximum value, respectively. Here is an example of working both of those methods:

```js
const smallest = Math.min(1, 5, 3, 9);
console.log(smallest); // 1

const largest = Math.max(1, 5, 3, 9);
console.log(largest); // 9
```

The first `console.log()` will log the number `1`, since `1` is the smallest in that list of numbers. And the second `console.log()` will log the number `9`, since `9` is the largest numbers in that list.

If you wanted to round numbers up or down to the nearest whole integer, you could use the `Math.ceil()` and `Math.floor()` methods. Here is an example of working with `Math.ceil()`:

```js
console.log(Math.ceil(4.3)); // 5
```

`Math.ceil()` will round `4.3` up to the nearest whole integer, which is `5` in this case. Now, let's take a look at rounding a number down:

```js
console.log(Math.floor(4.7)); // 4
```

`Math.floor()` will round `4.7` down to the nearest whole integer, which is `4` in this case. `Math.round()` is the hybrid of `Math.ceil()` and `Math.floor()`. It rounds a number to its nearest integer, taking the decimal point into account:

```js
console.log(Math.round(2.3)); // 2
console.log(Math.round(4.5)); // 5
console.log(Math.round(4.8)); // 5
```

So, if the decimal point is less than `5`, the number is rounded down. And if the decimal point is `5` or greater, the number is rounded up. A practical application of `Math.floor()` and `Math.random()` is to generate a random number between two whole numbers. Here's the syntax for that:

```js
Math.floor(Math.random() * (max - min)) + min;
```

Generating a random number between `20` and `1` would look like this:

```js
const randomNumBtw1And20 = Math.floor(Math.random() * 20) + 1;
console.log(randomNumBtw1And20); 
```

Another helpful `Math` method would be the `Math.trunc()` method. `Math.trunc()` removes the decimal part of a number, returning only the integer portion, without rounding:

```js
console.log(Math.trunc(2.9)); // 2
console.log(Math.trunc(9.1)); // 9
```

If you need to get the square root or cube root of a number, you can use the `Math.sqrt()` and `Math.cbrt()` methods, respectively:

```js
console.log(Math.sqrt(81)); // 9
console.log(Math.cbrt(27)); // 3
```

The first log statement, will log `9` because the square root of `81` is `9`, while the second log statement will log `3` because the cube root of `27` is `3`. If you need to get the absolute value of a number, you can use the `Math.abs()` method:

```js
console.log(Math.abs(-5)); // 5
console.log(Math.abs(5)); // 5
```

`Math.abs()` returns the absolute value of a number, turning negatives into positives. The last method we will look at will be the `Math.pow()` method:

```js
console.log(Math.pow(2, 3)); // 8
console.log(Math.pow(8, 2)); // 64
```

`Math.pow()` takes two numbers and raise the first to the power of the second. There are many more methods that belong to the `Math` object, that you can explore on your own. However, these are just a few of the more commonly used ones found in JavaScript codebases.



---
## Number constants

Here are some of the built-in number constants that exist on the Math object:

- The PI number: Math.PI which is approximately 3.14159
    
- Euler's number: Math.E which is approximately 2.718
    
- The natural logarithm of 2: Math.LN2 which is approximately 0.693
    

## Rounding methods

These include:

-  Math.ceil() - rounds up to the closest integer
    
-  Math.floor() - rounds down to the closest integer
    
-  Math.round() - rounds up to the closest integer if the decimal is .5 or above; otherwise, rounds down to the closest integer
    
-  Math.trunc() - trims the decimal, leaving only the integer
    

## Arithmetic and calculus methods

Here is a non-conclusive list of some common arithmetic and calculus methods that exist on the Math object:

- Math.pow(2,3) - calculates the number 2 to the power of 3, the result is 8 
    
- Math.sqrt(16) - calculates the square root of 16, the result is 4 
    
- Math.cbrt(8) - finds the cube root of 8, the result is 2 
    
- Math.abs(-10) - returns the absolute value, the result is 10 
    
- Logarithmic methods: Math.log(), Math.log2(), Math.log10() 
    
- Return the minimum and maximum values of all the inputs: Math.min(9,8,7) returns 7, Math.max(9,8,7) returns 9.
    
- Trigonometric methods: Math.sin(), Math.cos(), Math.tan(), etc.
    

## Logarithmic Methods

Math.log(x) - Returns the natural logarithm (base e) of x.

Math.log2(x) - Returns the base-2 logarithm of x.

Math.log10(x) - Returns the base-10 logarithm of x.

## Logarithmic Methods

Math.log(x) - Returns the natural logarithm (base e) of x.

Math.log2(x) - Returns the base-2 logarithm of x.

Math.log10(x) - Returns the base-10 logarithm of x.

## Conclusion

You can assign the results of JavaScript's Math functions to variables to store and reuse calculated values.

1

2

3

```javascript
var MyNum = Math.sqrt(16); // Calculates square root of 16

console.log(MyNum); // Output: 4

//This approach works for any Math function:

var MyNum = Math.pow(3, 4) will assign the value 81 to MyNum.
```

It is done to simplify the calculations, make your code cleaner, or use the results later.

Mark as completed

Like

Dislike

Report an issue