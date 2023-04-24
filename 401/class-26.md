# Intro to Django

### What are the key components of the Django framework, and how do they contribute to building a web application?

They key components of the Django framework are:

- URLs: Help map the website's pages and make sure the right page is shown when someone clicks a link.

- View:  Handles incoming HTTP requests from web browsers and decides what to show on the websites by returning HTTP responses.

- Models: Help store, manage and organize information in a database through adds, modifies and deletes, information like usernames and passwords.

- Templates: Determine the layout and design of the website, making it look pretty and organized, such as with HTML.

### Explain the role of Django’s MTV (Model-View-Template) architecture and how it handles a typical web request-response cycle.

Django's MTV (Model-View-Template) architecture is a way of organizing code in a web application that makes it easier to build and maintain.

In this architecture, the Model is responsible for managing data and the database. It defines the structure of data and how it's stored in the database.

The View handles incoming requests from web browsers and decides what to show on the website. It interacts with the Model to get the data it needs and passes it on to the Template.

The Template determines the layout and design of the website, making it look pretty and organized. It uses the data provided by the View to create the HTML page that is sent back to the user's web browser.

A simple example for this is when a user makes a request to a Django web application, the request is first handled by the View. The View interacts with the Model to get the data it needs and passes it on to the Template. The Template then creates the HTML page and sends it back to the user's web browser as a response.

### What is the purpose of Tailwind CSS, and how does it differ from Bootstrap CSS?

Tailwind CSS is a framework used for quickly building and customizing applications without having to write custom CSS. It uses a utility-first CSS framework design. These utility classes are used to control the layout, spacing, color, typography, shadows and more to create customized components and designs, all without writing a single line of custom CSS. 

Unlike Bootstrap, which has a pre-defined set of classes for each UI element, Tailwind provides a set of utility classes that can be combined to create custom styles. This makes it more flexible and customizable than Bootstrap.

## Things I want to know more about.

- I want to get more hands on experience with Django and Tailwind CSS.

- I want to know if you are able to use CSS frameworks like bootstrap, chakra or MUI with Django, and why Tailwind CSS is the best one. 



> References
>
>[Django Introduction](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Introduction)
>
>[Django Projects](https://www.djangoproject.com/start/)
>
>[How Django works behind the scenes](https://wsvincent.com/how-django-works-behind-the-scenes/)
>
>[What is Tailwind CSS](https://blog.hubspot.com/website/what-is-tailwind-css)
>
>[Writing your first Django app, part 1](https://docs.djangoproject.com/en/4.1/intro/tutorial01/)
>
>[Writing your first Django app, part 2](https://docs.djangoproject.com/en/4.1/intro/tutorial02/)
>
>[Tailwind CSS Django - Flowbite](https://flowbite.com/docs/getting-started/django/)