Accessing properties from nested objects involves using the dot notation or bracket notation, much like accessing properties from simple objects. However, you'll need to chain these accessors to drill down into the nested structure.

For example, let's consider a nested object representing a person with contact information:

```js
const person = {
  name: "Alice",
  age: 30,
  contact: {
    email: "alice@example.com",
    phone: {
      home: "123-456-7890",
      work: "098-765-4321"
    }
  }
};
```

To access `Alice`'s work phone number, you would chain the property accessors like this:

```js
console.log(person.contact.phone.work); // "098-765-4321"
```

You can also use bracket notation, which is particularly useful when property names include spaces or special characters, or when you're using variables to access properties.

```js
console.log(person['contact']['phone']['work']); // "098-765-4321"
```

Now, let’s take a look at how we can access data where one of the object properties has the value of an array. Here is a modified `person` object that includes an array of addresses:

```js
const person = {
  name: "Alice",
  age: 30,
  addresses: [
    { type: "home", street: "123 Main St", city: "Anytown" },
    { type: "work", street: "456 Market St", city: "Workville" }
  ]
};
```

Here is an example of how to access `Alice`'s work address city:

```js
console.log(person.addresses[1].city); // "Workville"
```

In this example, `person.addresses` refers to the array of addresses. To access the second address in that array, we use bracket notation and index `1`. Then, we use dot notation to access the `city` from that address object.

Understanding how to access properties in nested objects and arrays is essential when working with complex data structures. In future workshops and labs, you will have the opportunity to practice working with these types of data structures.