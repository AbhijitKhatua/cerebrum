What are regular expressions, and what are some common methods?

Regular expressions, or regex, are a feature supported by many different programming languages.

A regular expression is a special syntax to create a "pattern", which you can then use to check against a string, extract text, and more.

Let's take a look at a basic regular expression:

```js
const regex = /freeCodeCamp/;
```

Notice how, in JavaScript, you define a regular expression by creating your pattern between two forward slashes (`/`). Try not to confuse this with a comment, where the text comes after both forward slashes.

This particular regular expression will match the text `freeCodeCamp`, with capital `C`s, anywhere in a string. But how can you actually do that?

That brings us to our first method – the `test()` method. The `test()` method is present on `RegExp` objects, which are objects representing a regular expression (such as the one we just defined).

The `test()` method accepts a string, which is the string to test for matches against the regular expression. For example, let's try testing the string `e`:

```js
const regex = /freeCodeCamp/;
const test = regex.test("e");
console.log(test);
```

You can see we've called the `test()` method on our new regex, and passed the string `e` as the argument. We've also logged the result:

```js
console.log(test); // false
```

The `test()` method returned `false` because the string `e` does not match the pattern `freeCodeCamp`. Even though the pattern `freeCodeCamp` includes the letter `e`, that's the opposite direction of how regular expressions work.

Let's take a look at a few more examples. Take a moment to consider these:

```js
const regex = /freeCodeCamp/;
console.log(regex.test("freeCodeCamp"));
console.log(regex.test("freeCodeCamp is great"));
console.log(regex.test("I love freeCodeCamp"));
console.log(regex.test("freecodecamp"));
console.log(regex.test("FREECODECAMP"));
console.log(regex.test("free"));
console.log(regex.test("code"));
console.log(regex.test("camp"));
```

What do you think each line will print? Well, here's the result:

```js
const regex = /freeCodeCamp/;
console.log(regex.test("freeCodeCamp")); // true
console.log(regex.test("freeCodeCamp is great")); // true
console.log(regex.test("I love freeCodeCamp")); // true
console.log(regex.test("freecodecamp")); // false
console.log(regex.test("FREECODECAMP")); // false
console.log(regex.test("free")); // false
console.log(regex.test("code")); // false
console.log(regex.test("camp")); // false
```

Did that surprise you? Notice how the first three strings returned `true`. These strings all contain the text, `freeCodeCamp`, exactly, somewhere in the string.

Lines 5 and 6 return `false`. While they contain the text `freecodecamp`, the case does not match. Regular expressions are case-sensitive by default.

Finally, while the last three contain a portion of the pattern, the strings do not contain the entire pattern.

The `test()` method returns a `boolean`, indicating whether the string matches the regular expression at all.

But what if you wanted more information than that? Well, strings have a `match()` method. This method accepts a regular expression, although you can also pass a string which will be constructed into a regular expression.

`match()` returns the match array for the string. What's a match array? Well, let's take a look:

```js
const regex = /freeCodeCamp/;
const match = "freeCodeCamp".match(regex);
console.log(match);
```

If we run this, we get an array back! But it's a strange looking array. It's got some extra properties:

```js
console.log(match);
// [
//   'freeCodeCamp',
//   index: 0,
//   input: 'freeCodeCamp',
//   groups: undefined
// ]
```

The `groups` property would show any captured groups. You will learn what that means in a future lecture.

The `index` property tells you at what character in the string the match was found. In our case, it was found at the beginning of the string.

The `input` property tells you the string the `match()` method was called on.

Let's try a few more again, and see how the result changes:

```js
const regex = /freeCodeCamp/;
console.log("freeCodeCamp".match(regex)); // ['freeCodeCamp', index: 0, input: 'freeCodeCamp', groups: undefined]
console.log("freeCodeCamp is great".match(regex)); // ['freeCodeCamp', index: 0, input: 'freeCodeCamp is great', groups: undefined]
console.log("I love freeCodeCamp".match(regex)); // ['freeCodeCamp', index: 7, input: 'I love freeCodeCamp', groups: undefined]
console.log("freecodecamp".match(regex)); // null
console.log("FREECODECAMP".match(regex)); // null
console.log("free".match(regex)); // null
```

We know already that the first three strings should produce a match, so let's take a look at those:

```js
// ['freeCodeCamp', index: 0, input: 'freeCodeCamp', groups: undefined]
// ['freeCodeCamp', index: 0, input: 'freeCodeCamp is great', groups: undefined]
// ['freeCodeCamp', index: 7, input: 'I love freeCodeCamp', groups: undefined]
```

Is that what you expected? You can see how the `input` and `index` have changed depending on the string provided, and the location of the match in the string.

The other three lines, which do not match, return `null` instead of an array.

Now that we can test and match strings with our regular expression, what if we want to replace the content of a string? Maybe someone has written `freecodecamp` in all lowercase, and we want to automatically fix the casing for them.

First, we need to update our regular expression to match the lowercase form of `freecodecamp`, and create our test string:

```js
const regex = /freecodecamp/;
const str = "freecodecamp is rly kewl";
```

Now, strings have a `replace()` method which accepts two arguments: the regular expression to match (or a string, if you don't need all of the features of regex), and the string to replace the match with (or a function to run against each match).

So if we wanted to replace our `freecodecamp` with the proper casing:

```js
const regex = /freecodecamp/;
const str = "freecodecamp is rly kewl";
const replaced = str.replace(regex, "freeCodeCamp");
console.log(replaced);
```

And we'll peek at the result:

```js
console.log(replaced); // freeCodeCamp is rly kewl
```

You can see that `replace()` returns the updated string with the matching pattern `replaced`.

Regular expressions, and all of the methods associated with them, can seem complex and overwhelming. But you'll get the chance to explore them further in this next set of lectures.

## Common Regex Modifiers

What are some common regular expression modifiers used for searching?

Modifiers, often referred to as "flags", modify the behavior of a regular expression. Let's recall our example from an earlier lecture:

```js
const regex = /freeCodeCamp/;
console.log(regex.test("freeCodeCamp")); // true
console.log(regex.test("freeCodeCamp is great")); // true
console.log(regex.test("I love freeCodeCamp")); // true
console.log(regex.test("freecodecamp")); // false
console.log(regex.test("FREECODECAMP")); // false
console.log(regex.test("free")); // false
console.log(regex.test("code")); // false
console.log(regex.test("camp")); // false
```

If you remember, the all-lowercase and all-uppercase `freeCodeCamp` strings failed to match the pattern. This is because, by default, regular expressions are case-sensitive.

But what if we could tell the regular expression to be case-insensitive? Well, there's a modifier for that. The `i` flag makes a regex ignore case. How can we use it? Flags go after the closing forward slash in a regular expression:

```js
const regex = /freeCodeCamp/i;
```

Notice the change to the regular expression on the first line. Now we can check how this changes things:

```js
console.log(regex.test("freeCodeCamp")); // true
console.log(regex.test("freeCodeCamp is great")); // true
console.log(regex.test("I love freeCodeCamp")); // true
console.log(regex.test("freecodecamp")); // true
console.log(regex.test("FREECODECAMP")); // true
console.log(regex.test("free")); // false
console.log(regex.test("code")); // false
console.log(regex.test("camp")); // false
```

Because our regular expression is now case-insensitive, the all-lowercase and all-uppercase strings have "passed" the test. This can also work for a string with a random mix of uppercase and lowercase letters:

```js
console.log(regex.test("dO yOu LoVe fReEcOdEcAmP?")); // true
```

There are quite a few other flags that you can use. The `g` flag, or global modifier, allows your regular expression to match a pattern more than once.

Let's see how that affects our code. You'll notice we kept the `i` flag – a regular expression can use multiple flags (as many as needed) to achieve your desired behavior:

```js
const regex = /freeCodeCamp/gi;
```

Wait a second... what's this? It would seem that the global modifier is making some of our strings that should be passing fail instead:

```js
console.log(regex.test("freeCodeCamp")); // true
console.log(regex.test("freeCodeCamp is great")); // false
console.log(regex.test("I love freeCodeCamp")); // true
console.log(regex.test("freecodecamp")); // false
console.log(regex.test("FREECODECAMP")); // true
console.log(regex.test("free")); // false
console.log(regex.test("code")); // false
console.log(regex.test("camp")); // false
```

Why? Well, the global modifier makes your regular expression stateful. This means it keeps track of where it has previously matched a pattern. So when it matches the first `freeCodeCamp` string, it remembers that it found a match starting at index `0`.

We then test it against `freeCodeCamp is great`, but it doesn't start at index `0`. The regular expression "knows" it found a match at index `0` already, so even though this is a different string, it starts from the end index of the match.

`freeCodeCamp` is `12` characters long, so a match at `0` ends at index `11`. The matching will resume at index `12`. And since `is great` does not match `freeCodeCamp`, it returns `false`.

Then, because it fails to find a match, it "loses" its state and starts the following match back at `0`.

If we switch our logs around so that a string with the match at `0` is followed immediately by a string that has a match later than index `11`:

```js
console.log(regex.test("freeCodeCamp")); // true
console.log(regex.test("I loooooooove freeCodeCamp")); // true
```

When a regular expression is global, it gets a new property called `lastIndex`. Grabbing our previous code, let's see how this property works:

```js
console.log(regex.lastIndex); // 0
console.log(regex.test("freeCodeCamp")); // true
console.log(regex.lastIndex); // 12
console.log(regex.test("freeCodeCamp is great")); // false
console.log(regex.lastIndex); // 0
console.log(regex.test("I love freeCodeCamp")); // true
console.log(regex.lastIndex); // 19
console.log(regex.test("freecodecamp")); // false
console.log(regex.lastIndex); // 0
console.log(regex.test("FREECODECAMP")); // true
console.log(regex.lastIndex); // 12
console.log(regex.test("free")); // false
console.log(regex.lastIndex); // 0
console.log(regex.test("code")); // false
console.log(regex.lastIndex); // 0
console.log(regex.test("camp")); // false
```

Looking at this example, you can see how the state of the regular expression changes with each test call using the `lastIndex` to track its previous matches.

The global flag is great when you need to get multiple matches from a single string. But if you're testing multiple strings with the same regular expression it's best to leave the `g` flag off.

Before learning about the next flag, you need to learn about anchors. The carrot (`^`) anchor, at the beginning of the regular expression, says "match the start of the string":

```js
const start = /^freecodecamp/i;
```

The dollar sign (`$`) anchor, at the end of the regular expression, says "match the end of the string":

```js
const end = /freecodecamp$/i;
```

Take a moment to compare the outputs on the right:

```js
const start = /^freecodecamp/i;
const end = /freecodecamp$/i;
console.log(start.test("freecodecamp")); // true
console.log(end.test("freecodecamp")); // true
console.log(start.test("freecodecamp is great")); // true
console.log(end.test("freecodecamp is great")); // false
console.log(start.test("i love freecodecamp")); // false
console.log(end.test("i love freecodecamp")); // true
console.log(start.test("have met freecodecamp's founder")); // false
console.log(end.test("have met freecodecamp's founder")); // false
```

See how the start anchor only matches at the beginning of the string, and the end anchor only matches at the end of the string? But what about matching across multiple lines? Let's take a look at that:

```js
const start = /^freecodecamp/i;
const end = /freecodecamp$/i;
const string = `I really love
freecodecamp
it's my favorite`;
console.log(start.test(string)); // false
console.log(end.test(string)); // false
```

Even though `freecodecamp` is in there on its own line, it fails both tests. This is because, by default, anchors look for the beginning and end of the entire string.

But you can make a regex handle multiple lines with the `m` flag, or the multi-line modifier. Let's add that to our regular expressions to see what we get:

```js
const start = /^freecodecamp/im;
const end = /freecodecamp$/im;
const string = `I really love
freecodecamp
it's my favorite`;
console.log(start.test(string)); // true
console.log(end.test(string)); // true
```

Now they both match! Because the `freecodecamp` is entirely on its own line, the start anchor matches the beginning of that line, and the end anchor matches the end of that line.

Finally, you have the `d` flag, or indices modifier. Remember that the `i` flag is for case-insensitivity, so the indices modifier needed a different flag.

The `d` flag expands the information you get in a match object. Let's add it to our regular expression:

```js
const regex = /freecodecamp/di;
const string = "we love freecodecamp isn't freecodecamp great?";
console.log(string.match(regex));
```

And the result is:

```js
// [
//   'freecodecamp',
//   index: 8,
//   input: "we love freecodecamp isn't freecodecamp great?",
//   groups: undefined,
//   indices: [
//     0: [8, 20],
//     groups: undefined
//   ]
// ]
```

Our match object gets a new `indices` property! This property is an array of two numbers, the first being the index in the original string where the match starts, and the second being the index after the match ended. This array also has an extra `groups` property, which is also for named capture groups.

There are a few other flags that you should know are available to you, but are less common in typical code.

The first is the unicode modifier, or `u` flag. This expands the functionality of a regular expression to allow it to match special unicode characters.

You'll learn more about character classes in a later lecture, but the `u` flag gives you access to special classes like `Extended_Pictographic` to match most emoji:

```js
const regex = /🍎/u;

const str = "I have an apple 🍎";
console.log(regex.test(str)); // true
```

There is also a `v` flag, which further expands the functionality of the unicode matching.

The second is the sticky modifier, or the `y` flag. The sticky modifier behaves very similarly to the global modifier, but with a few exceptions.

The biggest one is that a global regular expression will start from `lastIndex` and search the entire remainder of the string for another match, but a sticky regular expression will return `null` and reset the `lastIndex` to `0` if there is not immediately a match at the previous `lastIndex`.

And the last is the single-line modifier, or the `s` flag. Remember that the multiline modifier allows start and end anchors to match the start and end of a line, instead of the entire string.

The single-line modifier allows a wildcard character, represented by a period (`.`) in regex, to match linebreaks – effectively treating the string as a single line of text.

There are quite a few of these modifiers, but the `i` and `g` flags are the ones you'll use most frequently, and are the most important to remember.