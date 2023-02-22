# APIs

## API Best Design Practice


- What does REST stand for?

Representational State Transfer

- REST APIs are designed around a ____.

REST APIs are designed around a resource, which are any kind of object, data, or service that can be accessed by a client.

- What is an identifier of a resource? Give an example.

An identifier is a URI that can uniquely identify a resource. Example of a URI for a particular customer order: https://adventure-works.com/orders/1

- What are the most common HTTP verbs?

GET, POST,PUT, PATCH, DELETE

- What should the URIs be based on?

The URIs should be based on the nouns, which are the resource and not the verbs, which are the actions on the resource.

- Give an example of a good URI.

https://google.com/search?q

- What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

It is when your web requests impose a load on the web server by having too many complex URIs that expose a large number of small resources.

- What status code does a successful GET request return?

200 (OK)

- What status code does an unsuccessful GET request return?

 404 (Not Found)

- What status code does a successful POST request return?

201 (Created)

- What status code does a successful DELETE request return?

204 (No Content)


## Things I want to know more about 

- Different types of versions of URIs for different types of media

>References
>
>[RESTful web API design](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design)