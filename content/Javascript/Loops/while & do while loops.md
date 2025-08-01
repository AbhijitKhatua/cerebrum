In previous lecture videos, you learned how to work with `for` loops, `for...in` loops and `for...of` loops. In this lecture, you will learn about the `while` loop and the `do...while` loop.

A `while` loop will run a block of code as long as the condition is true. Here is the basic syntax for a `while` loop:

```js
while (condition) {
  // code block to be executed
}
```

The condition is checked before the block of code is executed. If the condition is false, the block of code will not be executed.

`while` loops are useful when you do not know how many times you need to run the block of code. Here is an example of using a `while` loop to validate user input:

```js
let userInput = prompt("Please enter a number between 1 and 10");

while (isNaN(userInput) || Number(userInput) < 1 || Number(userInput) > 10) {
  userInput = prompt("Invalid input. Please enter a number between 1 and 10.");
}

alert("You entered a valid number!");
```

In this example, we are using the `prompt` method to ask for user input. Then, the `while` loop first checks if the `userInput` is `NaN`. Remember that `NaN` is "Not a Number". `isNaN` checks whether the value is `NaN` and that `NaN` is the result of an invalid number conversion because it's not a number.

So if the user types in random characters or nothing at all, then they will be prompted with the message again. The `while` loop is also checking if the `userInput`, when converted to a number, is between `1` and `10`.

We are using the `Number` constructor here because a prompt will return a string and we want only want to be explicitly checking numbers here.

If the user input is not between `1` and `10`, the `while` loop will continue to prompt the user to enter a number between `1` and `10`.

Once the user enters a valid number, the `while` loop will exit and an alert will be displayed to the user.

Another loop similar to the `while` loop would be the `do...while` loop. Here is the basic syntax:

```js
do {
  // code block to be executed
} while (condition);
```

One key difference between a `do...while` loop and a `while` loop is that the `do...while` loop will execute the block of code at least once before checking the condition.

If the condition is true, the block of code will continue to execute. If the condition is false, the block of code will stop executing.

Here is an example of using a `do...while` loop to validate user input:

```js
let userInput;

do {
  userInput = prompt("Please enter a number between 1 and 10");
} while (Number(userInput) < 1 || Number(userInput) > 10);

alert("You entered a valid number!");
```

In this example, we have a variable called `userInput` and have not assigned a value to it. Then we have a `do...while` loop that will prompt the user to enter a number between `1` and `10`.

Then the `while` loop will check if the user input is less `than` 1 or greater than `10`. If the input is not between `1` and `10`, the `do...while` loop will continue to prompt the user to enter a number between `1` and `10`.

Once the user complies and enters a valid number, the `do...while` loop will exit and an alert will be displayed to the user.

In most cases, you will probably use the `while` loop more often than the `do...while` loop. However, it is good to know both types of loops and when to use them.