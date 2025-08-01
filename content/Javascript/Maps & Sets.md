### Sets & WeakSets

In JavaScript, `Set` is a built-in object for managing data collections. It lets you store unique values of any type, whether primitive or object references. `Set` ensures that each value in it appears only once, making it useful for eliminating duplicates from an array or handling collections of distinct values.

As for `WeakSet`, it’s a special type of `Set` with fewer features that allows you to store weakly held object references and symbols. Unlike `Set`, `WeakSet` does not support primitives like numbers or strings.

Unlike a regular `Set`, a `WeakSet` only stores objects, and the references to those objects are "weak" meaning WeakSets do not prevent the stored objects from being garbage-collected if there are no other references to them. In simpler terms, if the object is not being used anywhere else in your code, it is removed automatically to free up memory.

To create a `Set`, you use the `Set` constructor and assign it to a variable:

```js
const myFirstSet = new Set();
```

You can also initialize the `Set` with values:

```js
const treeSet = new Set(['Baobab', 'Jackalberry', 'Mopane Tree', 'Breadfruit']);
```

If you log the `Set` to the console, this is what the output looks like:

```js
/*
Set(4) {'Baobab', 'Jackalberry', 'Mopane Tree', 'Breadfruit'}
  [[Entries]]
  0: "Baobab"
    value: "Baobab"
  1: "Jackalberry"
    value: "Jackalberry"
  2: "Mopane Tree"
    value: "Mopane Tree"
  3: "Breadfruit"
    value: "Breadfruit"
  size: 4
  [[Prototype]]: Set
*/
```

If you didn't initialize the `Set` with values, you can use the `add()` method to add an item to the `Set`:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');
```

The result and appearance of the result in the console remains the same.

Don't forget that duplicate items will be ignored in the `Set`:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');
treeSet.add('Baobab'); //duplicate item will be ignored

console.log(treeSet);
// Set(4) {'Baobab', 'Jackalberry', 'Mopane Tree', 'Breadfruit'}
```

The other methods you can use to manipulate a `Set` are:

- `delete()`
- `clear()`
- `has()`
- `entries()`
- `forEach()`
- `keys()`
- `values()`

Let's look at how these methods work one by one. `delete()` removes a specified item from the `Set`:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');

treeSet.delete('Breadfruit');

console.log(treeSet); // Set(3) {'Baobab', 'Jackalberry', 'Mopane Tree'}
```

`has()` checks if a specified value exists in the `Set`:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');

treeSet.delete('Breadfruit');

console.log(treeSet.has('Breadfruit')); // false
```

`entries()` returns a `Set` iterator containing an array of the values in a `[value, value]` format:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');

treeSet.delete('Breadfruit');

console.log(treeSet.entries());
// SetIterator {'Baobab' => 'Baobab', 'Jackalberry' => 'Jackalberry', 'Mopane Tree' => 'Mopane Tree'}
```

`keys()` and `values()` show the values in the `Set`. `keys()` is just an alias for the `values()` method:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');

treeSet.delete('Breadfruit');

console.log('Keys: ', treeSet.keys());
console.log('Values: ', treeSet.values());
// Keys: SetIterator {'Baobab', 'Jackalberry', 'Mopane Tree'}
// Values: SetIterator {'Baobab', 'Jackalberry', 'Mopane Tree'}
```

`forEach()` lets you iterate through the `Set`:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');

treeSet.delete('Breadfruit');

treeSet.forEach((tree) => console.log(tree));
/*
Baobab
Jackalberry
Mopane Tree
*/
```

`clear()` removes all the items of the array:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');

treeSet.delete('Breadfruit');

treeSet.clear();

console.log(treeSet); // Set(0) {size: 0}
```

It is also worth mentioning that there's a `size` property that returns the number of items in the `Set`:

```js
const treeSet = new Set();

// Add items to the treeSet
treeSet.add('Baobab');
treeSet.add('Jackalberry');
treeSet.add('Mopane Tree');
treeSet.add('Breadfruit');

treeSet.delete('Breadfruit');

console.log(treeSet.size); // 3
```

Just like `Set`, there's also a `WeakSet` constructor you can use to create a `WeakSet`:

```javascript
const treeWeakSet = new WeakSet();
```

`WeakSet` also has the `add()`, `delete()`, and the `has()` methods:

```javascript
const treeWeakSet = new WeakSet();

treeWeakSet.add({ name: 'Baobab' });
treeWeakSet.add({ name: 'Jackalberry' });
treeWeakSet.add({ name: 'Mopane Tree' });
treeWeakSet.add({ name: 'Breadfruit' });

treeWeakSet.delete('Jackalberry');
console.log(treeWeakSet.has('Jackalberry')); // false

console.log(treeWeakSet);
```

In the output, the contents of the `WeakSet` appear like this:

```javascript
/*
WeakSet {{…}, {…}, {…}, {…}}
  [[Entries]]
    No properties
  [[Prototype]]: WeakSet
    .
    .
    .
*/
```

The contents appear empty because WeakSets are not iterable and do not expose their contents directly.

Don't forget that only symbols and objects with well-defined keys and values are supported. Adding a primitive, such as numbers or strings, will result in an error:

```js
treeWeakSet.add('Alan Smith');

console.log(treeWeakSet); // Invalid value used in weak set
//    at WeakSet.add (<anonymous>)
```

The key difference between a `Set` and a `WeakSet` is that a `Set` stores any value, while a `WeakSet` can only store objects.

Here are some other noticeable differences between a `Set` and a `WeakSet`:

|Feature|Set|WeakSet|
|---|---|---|
|Type of Values Stored|Stores any data type|Stores only objects|
|Referencing|Strong referencing|Weak referencing|
|Iteration|Supports iteration with `forEach` and loops|Does not support iteration|
|Methods and Properties|`add()`, `delete()`, `has()`, `keys()`, `values()`, `size`, and more|`add()`, `delete()`, and `has()` only|
|Use case|General-purpose collection of unique values and removing duplicates from arrays|Efficient memory tracking of object references|

You can see the differences in the types of values that the two kinds of sets can store, their support for iterating over the stored objects and their ideal use cases. Please take a moment to read the content of this table.

### Maps & WeakMaps
What is the Map object, and how does it differ from WeakMaps?

In JavaScript, a `Map` is a built-in object that stores key-value pairs, similar to an object. However, it differs from standard JavaScript objects by allowing keys of any type, including objects and functions.

A `WeakMap` is a collection of key-value pairs, similar to a `Map`, but it uses weak references for its keys. The keys must be objects, while the values can be of any type.

Think of the relationship between a `WeakMap` and a `Map` as similar to the relationship between a `WeakSet` and a `Set`, as you learned in the previous lecture.

To create a `Map`, you use the `Map()` constructor prepended with the `new` keyword:

```js
const myFirstMap = new Map();
```

You can initialize the Map with values:

```js
const myTreesMap = new Map([
 [{ type: 'deciduous' }, 'Maple tree'],
 [['forest', 'grove'], 'Pine tree'],
 [42, 'Oak tree'],
 [true, 'Birch tree'],
 [function() { return 'I am a function key'; }, 'Willow tree'],
]);
```

If you didn't initialize the `Map` with values, you can use the `set()` method to add them:

```js
const myTreesMap = new Map();
myTreesMap.set({ type: 'deciduous' }, 'Maple tree');
myTreesMap.set([1, 2], 'Pine tree');
myTreesMap.set(42, 'Oak tree');
myTreesMap.set(true, 'Birch tree');
myTreesMap.set(function() { return "I'm a function key"; }, 'Willow tree');

console.log(myTreesMap);
```

Here's what a `Map` looks like in the console:

```js
/*
Map(5) {{…} => 'Maple tree', Array(2) => 'Pine tree', 42 => 'Oak tree', true => 'Birch tree', ƒ => 'Willow tree'}
  [[Entries]]
    0:{Object => "Maple tree"}
      key: {type: 'deciduous'}
      value: "Maple tree"
    1:{Array(2) => "Pine tree"}
      key: (2)
      value: "Pine tree"
    2:{42 => "Oak tree"}
      key: 42
      value: "Oak tree"
    3:{true => "Birch tree"}
      key: true
      value: "Birch tree"
    4:{function () { return "I'm a function key"; } => "Willow tree"}
      key: f ()
      value: "Willow tree"
    size: 5
    [[Prototype]]: Map
*/
```

Other methods you can use to work with a `Map` are:

- `get(key)` to retrieve the value associated with the specified `key`.
- `has(key)` to check if a `key` exists in the `Map`.
- `delete(key)` to remove a key-value pair from the `Map`.
- `clear()` to remove all key-value pairs.
- `entries()` to check the entries of the `Map` (it returns the entries in a `MapIterator`).
- `forEach()` to loop through the entries of the `Map`.
- `size` to indicate the number of key-value pairs in the `Map`.

There's a `WeakMap()` constructor you can use to create a `WeakMap`:

```js
const myFirstWeakMap = new WeakMap();
```

The `set()`, `get()`, `has()`, and `delete()` methods are all available for use with a `WeakMap` as well. For example here's how you can assign items to the `Map` with the `set()` method:

```js
const myTreeWeakMap = new WeakMap();

myTreeWeakMap.set({ id: 1 }, 'Maple tree');
myTreeWeakMap.set({ id: 2 }, 'Pine tree');
myTreeWeakMap.set({ id: 3 }, 'Oak tree');
myTreeWeakMap.set({ id: 4 }, 'Birch tree');
myTreeWeakMap.set({ id: 5 }, 'Willow tree');

console.log(myTreeWeakMap);
```

Here's what a `WeakMap` looks like in the console:

```js
/*
WeakMap {{…} => 'Willow tree', {…} => 'Maple tree', {…} => 'Pine tree', {…} => 'Oak tree'}
  [[Entries]]
    No properties
  [[Prototype]]: WeakMap
*/
```

Here are the differences between a `Map` and a `WeakMap`:

|**Feature**|**Map**|**WeakMap**|
|---|---|---|
|**Key Type**|Keys can be of any data type, including strings, numbers, objects, or even functions.|Keys must be objects.|
|**Use Case**|Use a `Map` when you need to associate data with any type of key.|Use a `WeakMap` when you only need to associate data with objects.|
|**Iteration**|You can loop through a `Map` using `forEach()`, `keys()`, `values()`, or `entries()`.|A `WeakMap` is not iterable.|
|**Size Property**|`Map` has a `size` property to get the number of key-value pairs.|`WeakMap` does not have a `size` property.|

In the table above, you can see the differences summarized including the key type, use case, iteration and size property. Please take a moment to read the content of this table to learn more about their differences.