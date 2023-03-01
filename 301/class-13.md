# More CRUD

## CRUD basics

- Which HTTP method would you use to update a record through an API?

You would use the UPDATE method.

- Which REST methods require an ID parameter?

The DELETE and the UPDATE method requires an ID parameter. /thing/:id

- What’s the relationship between REST and CRUD?

From what I can tell, the REST API portion of the application is the part that controls where or what data is being manipulated. CRUD is when you define a function or method to happen to the data. 

So REST are the nouns/resources.<br/>
CRUD are the verbs/actions to the resources.<br/>

- If you had to describe the process of creating a RESTful API in 5 steps, what would they be?

1. Organize the resources into URI's (/things)
2. Define a schema for that resource, this will be used for front and back end requests and responses
3. Create HTTP request methods (CRUD) to the URI Endpoints. Include: req, res at a minimum.
4. Create a response status code for the request upon success and failure
5. Connect to a database/port that will decide where the response is going and how it is going to be formatted for front end


### What I want to know more about

- What makes a RESTful API stateless and how to keep them indepenedent from each other

- Best practices of middleware coding, such as app.get()

>References
>
>[CRUD Operations Explained](https://medium.com/geekculture/crud-operations-explained-2a44096e9c88)
>
>[SPEED RUN: Build a CRUD API with Node.js + Express + MongoDB](https://www.youtube.com/watch?v=EzNcBhSv1Wo)