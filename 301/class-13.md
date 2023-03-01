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

1. Create an express app, (npx create-express-api server) and install packages, dependencies, etc. (mongo, nodemon, cors, dotenv)

2. Define a schema for that resource, created in a separate file this will be used for front and back end requests and responses and how we receive the response or send out request.

```javascript
// this will be in a seperate folder, usually a models folder in a file called ThingModel.js

const mongoose = require('mongoose');

const thingSchema = new mongoose.Schema({
    name: {
        type: String,
        required: true
    },
    isCool: {
        type: Boolean,
        required: true
    }
});

module.exports = mongoose.model('Thing', thingSchema)

```

3. Organize the resources into URI's (/things) and have separate .js files for each resourceInclude: req, res at a minimum. Create HTTP request methods (CRUD) to the URI Endpoints. Create a response status code for the request upon success and failure

```javascript
// This will be in routes or modules folder inside of a things.js
const express = require('express');
const Thing = require('../models/ThingModel')

const router = express.Router();

router.get('/things', async (request, response) => {
    try {
        const thing = await Thing.find();
        response.status(200).json(thing);
    } catch (error) {
        response.status(500).json('server side error')
    }
})

module.exports = router;

```

4. In Express app, set up the required middleware, routes and URI's and mount it to the server.js, connect to database:

```javascript
// this will be in our server.js file
require('dotenv').config()
const express = require('express');
const cors = require('cors');
const app = express();
const Things = require('./routes/things');

const PORT = process.env.PORT
const MONGO_DB_URI = process.env.MONGO_DB_URI;

app.use(cors());
app.use(express.json());

app.use('/', Things)

mongoose.connect(DATABASE_URL)
  .then(() => {
    app.listen(PORT, () => console.log(`Connected to mongodb and listening on ${PORT}`));
  })
  .catch((error) => {
    console.log(error);
  });
  
```

5. Create a .env and create a PORT variable, for testing, later connect to a database with the environment variable.

```
NODE_ENV=development
PORT=3001
MONGO_DB_URI=mongodb+srv://lskjdlfjjwieff//somecrazyurlstufff
```





### What I want to know more about

- What makes a RESTful API stateless and how to keep them indepenedent from each other

- Best practices of middleware coding, such as app.get()

>References
>
>[CRUD Operations Explained](https://medium.com/geekculture/crud-operations-explained-2a44096e9c88)
>
>[SPEED RUN: Build a CRUD API with Node.js + Express + MongoDB](https://www.youtube.com/watch?v=EzNcBhSv1Wo)