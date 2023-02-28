# CRUD

## Status Codes on REST Methods

- In your own words, describe what each group of status code represents:

100’s = These codes will give us information. Telling us that something may not be fully loaded yet as the server tries to send it.
200’s = These are successful requests codes. 
300’s = Redirect; makes browser send NEW request to supplied address
400’s = Client side error (bad request in some way, like  requesting non-existent resource) or bad URL
500’s = server side error (some code error on the server side, or server might be down)


- What is a status code 202?

Often used for asynchronous processing. This code tells the client that the request was valid, but its processing will finish sometime in the future. The response body should include an URL to the finished resource with some information about when it will be available, or an URL to some monitoring endpoint that tells the client when the resource is available.

- What is a status code 308?

Permanent Redirect - This is the right code if the resource will now be available at a new URL and the client should directly access it via the new URL in the future. The current endpoint can’t control the clients’ behavior after the request and a subsequent redirect if the resource URL changes again have to be issued from the new URL.


- What code would you use if an update didn’t return data to a client?

I would use a code 204

- What code would you use if a resource used to exist but no longer does?

I would use a code 410

- What is the ‘Forbidden’ status code?

Code 403

## Building REST API with Node.js, Express & MongoDB


- Why do we need to pull our MongoDB database string out of our server and put it into our .env?

So we do not show our database string to the public when it is ignored on our .gitignore since it contains sensitive information

- What is middleware?

Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. The next middleware function is commonly denoted by a variable named next.

- What does app.use(express.json()) do?

app.use() function adds new middleware to the app. express.json() is a built in middleware function in Express that parses incoming JSON requests and puts the parsed data in 'req.body'. Combining the two, we are adding the new middleware to the map with the ability to parse JSON. 

- What does the /:id mean in a route?

It is a more dynamic route that will fill in with whatever the id is.

- What is the difference between PUT and PATCH?

The PUT method is used to create, change or overwrite something at a specific URL, such as changing a whole object.

The PATCH method is used to make partial changes to something without changing the whole data at a specific URL, such as a value. 

- How do you make a default value in a schema?

You can specify a default with the keyword 'default' like this:

```javascript

const schema = new Schema({
    name: { type: String, default: 'user'}
})

```

- What does a 500 error status code mean?

500 error status code means a server side error. 

- What is the difference between a status 200 and a status 201?

Status code 200 means everything is successful. Status code 201 means something was successfully created. 

>References
>
>[Status Codes Based On REST Methods](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)
>
>[Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/watch?v=fgTGADljAeg)
>
>[Using middleware](https://expressjs.com/en/guide/using-middleware.html)