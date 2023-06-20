Using appropriate HTTP verb is very important in designing REST APIs.
Here's a quick overview of best practices for designing REST APIs

When creating resources, POST or PUT requests can be used. It's important to note that POST requests are not idempotent, as they are used for creating new resources each time they are called.

For reading resources, GET or POST requests can be used. POST requests are particularly helpful when the number of parameters is high, or the values of parameters are not easily exposable in a GET request.

When updating resources, PUT or PATCH requests can be used. PATCH requests are useful for partial updates.

Finally, for deleting resources, obviously DELETE requests should be used.