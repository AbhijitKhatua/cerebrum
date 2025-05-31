What is the Fetch API and what are common types of resources that are fetched from the network?

The Fetch API allows web apps to make network requests, typically to retrieve or send data to the server. This API provides a `fetch()` method that you can use to make these requests. Let's look at a basic example of how to use `fetch`:

```js
fetch('https://api.example.com/data')
```

In this example, we're making a `GET` request to `https://api.example.com/data`. This will then return us some data that we need to convert to JSON format and can use anywhere we want to.

By default, the Fetch API uses the `GET` method to retrieve data. This will be covered in the next lecture, along with other common HTTP request methods.

Now, let's discuss some common types of resources that are fetched from the network.

In our web apps, we need some common data like weather data, professions list data, country names list, country code or country flag icons/images. Using these data we can make our app more informative and interactive. Thanks to Fetch API, we can get these resources from the network.

Images are some frequently fetched resources. You might use fetch to load images statically or dynamically based on user actions, and display them on your web app.

Text files are another type of resource often fetched. This could include configuration files, log files, or even entire documents that you want to display on your webpage.

In some cases, you might fetch audio or video files. The Fetch API can handle these types of resources as well, allowing you to work with a wide variety of data types.

let's discuss about the `GET`, `POST`, `PUT` and `DELETE` HTTP methods of Fetch API.

Let's start with the most common HTTP method which is the `GET` method. This is used to retrieve data from a server. When you use `fetch()` without specifying a method, it defaults to `GET`.

```js
fetch('https://api.example.com/data')
```

In this code, we're making a `GET` request to `https://api.example.com/data`. Now, please note that you cannot use this data directly, you have to convert the response to a JSON format. Only then you can use it anywhere you want in your project. Here’s an example of how to do it:

```js
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
```

In this code, the response coming from the Fetch API is a promise, and we are using a `.then` handler to convert the response to a JSON format. In a prior lecture video, you learned that a `Promise` is an object that represents the eventual completion (or failure) of an asynchronous process and its value.

The value of a promise is not known when the promise is created. It’s only known when the asynchronous process is completed. When we chain the two `.then` handlers to the fetch call, this is something called promise chaining which will be taught in the next lecture.

So far we have been retrieving resources from a server. But, did you know that we can also send data to the server? The `POST` method is used to send data to a server to create a resource. Here’s an example of a `POST` method which is used to create data into the server:

```js
fetch('https://api.example.com/users', {
  method: '`POST`',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    name: 'John Doe',
    email: 'john@example.com'
  })
})
```

In this example, we're sending a `POST` request to create a new user. We specify the method as `POST`, set the appropriate headers, and include a `body` with the data we want to send. The body needs to be a string, so we use `JSON.stringify()` to convert our object to a JSON string.

The `PUT` method is used to update existing resources of a server. Here’s an example:

```js
fetch('https://api.example.com/users/45', {
  method: '`PUT`',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    name: 'John Smith',
    email: 'john@example.com'
  })
})
```

In this example, look carefully at the URL, you can see a `45` at the end. This is typically used as a unique ID to identify the data we are trying to update. We used the `PUT` method on the code and also specified the data as the `body` which will be used to update the identified data.

The `DELETE` method is used to delete a resource from the server. Here’s an example:

```js
fetch('https://api.example.com/users/45', {
  method: '`DELETE`',
})
```

In this code, we are including the `DELETE` method and an ID at the end of the url to identify the data which needs to be deleted.