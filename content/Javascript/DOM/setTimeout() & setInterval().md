How do the `setTimeout()` and `setInterval()` methods work?

When building your programs, you'll often want something to happen after a delay, or repeat at regular intervals. That's where the `setTimeout()` and `setInterval()` methods come in handy. Both methods accept two parameters: a function and a delay.

Let's look at each of the methods in more detail so you can start using them in your web projects. 

`setTimeout()` lets you delay an action for a specified time. Here's the basic syntax of the `setTimeout()` method:

```js
setTimeout(functionToRun, delay);
```

`functionToRun` is the code you want to execute after a specified delay, and `delay` is the time (in milliseconds) to wait before running the function. Here's an example:

```js
setTimeout(function () {
 console.log("This runs after 3 seconds");
}, 3000);
```

You can also use an arrow function for the callback, like this:

```js
setTimeout(() => {
 console.log("This runs after 3 seconds"); 
}, 3000);
```

`setInterval()` keeps repeating a function at a set interval. It's like having an alarm that goes off every few seconds. `setInterval()` is perfect when you want something to happen over and over again, like refreshing data or creating an animation that moves continuously.

Just like `setTimeout()`, it takes a function and a delay:

```js
setInterval(functionToRun, delay);
```

`functionToRun` is the code you want to run repeatedly, while `delay` is the time in milliseconds between each execution of that function. Here's an example:

```js
setInterval(() => {
 console.log("This runs every 2 seconds");
}, 2000);
```

And here's the result in the console:

```md
This runs every 2 seconds
This runs every 2 seconds
This runs every 2 seconds
```

Since `setInterval()` keeps executing the provided function at the specified interval, you might want to stop it. To do this, you have to use the `clearInterval()` method.

To do the work, `clearInterval()` takes the ID of the `setInterval()` you want to stop. This could be a variable you assign the interval to. One way to stop the interval is inside a `setTimeout()`, as that will stop the interval after a certain time:

```js
const intervalID = setInterval(() => {
 console.log("This will stop after 5 seconds");
}, 1000);

setTimeout(() => {
 clearInterval(intervalID);
}, 5000);
```

You can also stop a timeout with the `clearTimeout()` method:

```js
let timeoutID = setTimeout(() => {
 console.log("This will not run");
}, 5000);

clearTimeout(timeoutID);
```

With that code, the `setTimeout()` will not run at all. So, a more elegant way to do it is through the DOM, by adding a click event listener to a button to stop the timeout:

```html
<h1>Cancel Timeout Example</h1>
<button id="cancelButton">Cancel Timeout</button>

<script>
   let timeoutID = setTimeout(() => {
     console.log("This will run if not canceled");
   }, 5000);

   document
   .querySelector("#cancelButton")
   .addEventListener("click", () => {
     clearTimeout(timeoutID);
     console.log("Timeout canceled!");
   });
</script>
```