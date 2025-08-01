What is the purpose of the `preventDefault()` method?

Let's learn about the purpose of the `preventDefault()` method on events.

Every event that triggers in the DOM has some sort of default behavior. The `click` event on a checkbox toggles the state of that checkbox, by default. Pressing the space bar on a focused button activates the button. The `preventDefault()` method on these event objects stops that behavior from happening.

Let's take a look at an example. Let's define an `input` element for a user to type in:

```html
<label>Enter some characters:
  <input type="text">
</label>
```

And if we look at the result, we can type in the input field as expected. But maybe we don't want that. Maybe, instead, we'd like to show the character the user types in a separate element. First, let's define our element for that:

```html
<label>Enter some characters:
  <input type="text">
</label>
<p id="output"></p>
```

And then, we need to hook into the `keydown` event to listen for a character being typed on the keyboard. Note that we do not want the `change` or `input` events here, because we need the keyboard information.

```javascript
const input = document.querySelector("input");

input.addEventListener("keydown", (e) => {
    
})
```

The `keydown` event fires when you press down on a keyboard key. When this happens, let's display the character in our `p` element.

```javascript
const input = document.querySelector("input");
const output = document.getElementById("output");

input.addEventListener("keydown", (e) => {
  output.innerText = `You pressed the ${e.key} key`;
});
```

`e.key` gives you the value of the key pressed, such as `a` for the `a` key or `Enter` for the `Enter` key.

With the above code, when you type in the `input`, the character you type will be displayed in the `p` element.

This is great, but we don't want to show the characters in the `input` as well. This is where our `preventDefault()` method comes in. The default behavior of a `keydown` is to render the character in the input. Let's avoid that by calling `e.preventDefault()`:

```javascript
const input = document.querySelector("input");
const output = document.getElementById("output");

input.addEventListener("keydown", (e) => {
  e.preventDefault();
  output.innerText = `You pressed the ${e.key} key`;
});
```

And just like that, you have prevented the default behavior to allow yourself to implement your own custom event handling.

Another common example of when to use the `e.preventDefault` method has to deal with form submissions. By default, submitting a form sends data to the server and reloads the page. Using `e.preventDefault()` prevents this from happening.

```js
const form = document.querySelector("form");

form.addEventListener("submit", (e) => {
  e.preventDefault();
  // rest of code goes here
});
```

Preventing the default behavior is great when you need more control over how a user interacts with the page, but it's important to keep things like accessibility in mind – your custom behavior should provide the same features as the default.