# REST

## Explaining REST


- Who is Roy Fielding?

He helped write the first web servers, that sent documents across the internet and then he did a ton of research explaining why the web works the way it does. His name is on the specification for the protocol that is used to get pages from servers to your browser.

- Why don’t the techniques that we use in this class work well when we need to be able to talk to all of the machines in the world?

Because we use a local live server instead of a live site that has a live url during development. So we are just sending requests to and from local pages that we created and from data that we statically entered.

- What is the HTTP protocol that Fielding and his friends created?

Its a protocol that the browser reads and knows what to use, it knows to redirect users to certain URLs and to retrieve information from other HTML pages to display for the user through applying verbs (GET, POST, PUT, PATCH) to nouns (pages).

- What does a GET do?

When a machine GETs a resource(URL), it will ask for the machine-readable one. When a browser GETs a resource for a human, it will ask for the human-readable "representation" of that data.

- What does a POST do?

Its used to add something/information to another system.

- What does PUT do?

Its used to replace something in another system.

- What does PATCH do?

Patch is used to do a partial update on something in another system.



>References
>
>[How I explained REST to my brother](https://gist.github.com/brookr/5977550)

## Things I want to learn more about

- How to implement the GET, POSt, PUT, PATCH to my webpages and when I should use them