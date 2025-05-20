What is the DOM, and how do you access elements?

Let's learn about the DOM and why it's so important for web development. DOM stands for Document Object Model. It's a programming interface that lets us interact with HTML documents.

With the DOM, you can [[Create Modify Node]], or delete elements on a webpage. You can even make your website interactive by making elements listen to and respond to events.

In the DOM, an HTML document is represented as a tree of nodes. Each node represents an HTML element from the HTML document:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>DOM Example</title>
  </head>
  <body>
    <h1>What is the DOM?</h1>
    <h2>Let's learn about the DOM</h2>
  </body>
</html>
```

This is a diagram representing the basic DOM structure of our example:

```md
Document
========

HTML
-----

- Head
  - Title
- Body
  - H1
  - H2   
```

Of course, this can be more detailed and complex based on the structure of the HTML markup of a webpage.

The HTML document is the root node in the DOM hierarchy. It has one child node, the `html` element. This is the root element of the HTML document, since all other nodes descend from it.

The `html` element has two children: `head` and `body`.

The `head` element contains metadata about the document. It provides essential information about the webpage.

The `body` element contains the visible content of the webpage.

You can access these elements with JavaScript, work with them in your code, and even modify them dynamically. That's the power of the DOM and web APIs.

To access these elements in JavaScript, you can use `getElementById()` and `querySelector()` methods. These methods are web APIs because they provide standardized ways to interact with the DOM using JavaScript.

With `getElementById()`, you can get an object that represents the HTML element with the specified `id`. Remember that `id`s must be unique in every HTML document, so this method will only return one `Element` object. Here you can see an example:

```js
const container = document.getElementById("container");
```

This line of JavaScript code gets an element with the `id` value of `container` and assigns that object to a JavaScript constant. You must pass the `id` within quotation marks as an argument. If you log this object to the console, you will see it in the output:

```js
console.log(container); // <div id="container">...</div>
```

`querySelector()` is broader than `getElementById()`. With `querySelector()`, you can get the first element in the HTML document that matches the CSS selector passed as argument. In this example, you will get the first element with the class `section` and assign it to a variable:

```js
const section = document.querySelector(".section");
```

You also have other methods to match multiple elements, like `getElementsByClassName()` and [[querySelectorAll()]]. You'll learn more about them in a coming module.

By understanding how to use web APIs to manipulate the DOM efficiently, you can create powerful and interactive web applications.

How do DOM nodes exist relative to each other in the DOM Tree?

Let's learn about DOM nodes and their relationships in the DOM tree.

Just as a real tree has large and small branches connected in a hierarchical structure, DOM nodes also have direct and indirect relationships with one another. We will use this example to illustrate these relationships:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>DOM Tree Example</title>
  </head>
  <body>
    <h1>Heading 1</h1>
    <p>Paragraph 1</p>
    <ul>
      <li>List item 1</li>
      <li>List item 2</li>
    </ul>
  </body>
</html>
```

Let's start at the top. The root of the DOM tree is the `html` element. It's the top-level container for all the content of an HTML document. All other nodes are descendants of this root node.

Then, below the root node, we find other nodes in the hierarchy. A parent node is an element that contains other elements. A child node is an element that is contained within another element.

In this example, the `body` element is the parent of the paragraph element while the paragraph element is a child of the `body` element. These elements are represented as nodes in the DOM tree with the same relationships.

Just like we have parent nodes and child nodes, we also have sibling nodes. Sibling nodes are elements that share the same parent. In our example, two list item elements share the same unordered list parent, so they are siblings.

Similarly, the `h1` and paragraph elements are siblings because they share the same parent, the `body` element.

We also have indirect relationships across different levels in the hierarchy. Descendant nodes are elements that are contained within another element, either directly or indirectly. An element is considered a descendant of another one if it can be reached by going through the DOM tree downwards from its ancestor.

In our example, the list item `li` elements are descendants of the `body` element, since they are indirectly contained within it.

An ancestor node is an element that is higher up in the DOM tree hierarchy than another element. In our example, the `body` element is an ancestor of the list item `li` elements.

Understanding these relationships is essential for manipulating and navigating the DOM tree using JavaScript.

[[Diff in innerText, textContent, and innerHTML]]
[[Remove Nodes]]
[[Navigator, Window, and Document]]
[[Event Object]]
[[Manipulate Styles]]
[[Canvas API]]
[[requestAnimationFrame() API]]
[[Web Animations API]]