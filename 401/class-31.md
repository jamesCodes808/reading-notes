# Django REST Framework & Docker

## What are the key components of a Docker container, and how do they help streamline the development and deployment of applications?

Docker Containers are a type of virtualization and a running instance of a Docker image. 

So the key components of a Docker container are:

- Dockerfile: This is a list of image instructions. The file/'recipe' that will define the image and is used to build the image. Read from top-to-bottom. First instruction MUST be the `FROM` command, which is importing a base image (can be premade or one that we customly made).

```
$ touch Dockerfile 
```

```
# Dockerfile
FROM python:3.7-alpine
```

- Image: This is a snapshot of the Dockerfile/'recipe' at a given time. Images can be made up of one or more image layers. With Image layers, you usually want to layer the code that won't change too often at the top. 

How we build the image for the first time. 
```
$ docker image build .
```

- docker-compose.yml: This file is a list of container instructions. Explains controls on how to run the container.

first we create a Django app from scratch, assuming pipenv is installed.

```
$ cd ..
$ mkdir djangoapp && cd djangoapp
$ pipenv install django==3.0
$ pipenv shell

```

This will create a `pipfile` and a `pipfile.lock`. 
Then we create a project in the current directory.

```
(djangoapp) $ django-admin startproject example_project .
```

Now we can use runserver command on the new project

```
(djangoapp) $ python manage.py runserver
```

Now that we have a project, we can create a Dockerfile for the images we made which completely replaces the local dev environment, and add a `docker-compose.yml` for the container instructions.

```
$ touch Dockerfile
$ touch docker-compose.yml
```

The `Dockerfile` has a couple commands such as `RUN`, `COPY` and `ADD`. Each creates a new layer.

```
# Dockerfile

# Python version
FROM python:3.7-alpine

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set work directory
WORKDIR /code

# Install dependencies
COPY Pipfile Pipfile.lock /code/
RUN pip install pipenv && pipenv install --system

# Copy project
COPY . /code/

```

In the `docker-compose.yml` we want to specify the instructions for the container and what services they are going to run inside of a container.

```
# docker-compose.yml
version: '3.7'

services:
  web:
    build: .
    command: python /code/manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - 8000:8000
```

This will streamline the development and deployment of applications because we are telling the overall Docker Container to build the image, run the container and run the web application with one command

```
$ docker-compose up --build
```

## Describe the primary steps involved in building a library website using Django, including essential components like models, views, and templates.

To build a basic library website using traditional Django:

1. Set up the project

    - Navigate to existing code dir (make sure you are not in a virtual env).
    - Create a new directory `library`, create new virtual environment, activate it, and install Django

    ```
    # Windows
    > cd onedrive\desktop\code
    > mkdir library
    > cd library
    > python -m venv .venv
    > .venv\Scripts\Activate.ps1
    (.venv) > python -m pip install django~=4.0.0

    # macOS
    % cd desktop/desktop/code
    % mkdir library
    % cd library
    % python3 -m venv .venv
    % source .venv/bin/activate
    (.venv) % python3 -m pip install django~=4.0.0
    ```

    - Create a new project with `startproject` command.

    ```
    (.venv) > django-admin startproject django_project .
    ```

    - `migrate` to sync the database with Django's settings, and start the server with `runserver`

    ```
    (.venv) > python manage.py migrate
    (.venv) > python manage.py runserver
    ```

2. Create the first app

    - Add the first app using the `startapp` command outside of the virtual environment.

    ```
    (.venv) > python manage.py startapp sample_app
    ```

    - make sure to create an `urls.py` file in the app dir. And the app name to the project directory `settings.py` `INSTALLED_APPS` section

3. Create your app Models

    - Go to your `sample_app/models.py` in the app dir, and create the model of your object.

    For example, creating a Book model

    ```python
    # sample_app/models.py
    from django.db import models


    class Book(models.Model):
        title = models.CharField(max_length=250)
        subtitle = models.CharField(max_length=250)
        author = models.CharField(max_length=100)
        isbn = models.CharField(max_length=13)

        def __str__(self):
            return self.title
    ```

    - run `makemigrations` to create a migration file for our new database model. 

    ```
    (.venv) > python manage.py makemigrations sample_app
    ```

    - run `migrate` to migrate and apply it to the database. 

4. Have things working on the Admin side to manage the database models

    - use the `createsuperuser` command

    ```
    (.venv) > python manage.py createsuperuser
    ```

    - update app dir `admin.py` file

    ```python
    # sample_app/admin.py
    from django.contrib import admin

    from .models import Book

    admin.site.register(Book)
    ```

    - run server again with `runserver` command

    ```
    (.venv) > python manage.py runserver
    ```

    - on webpage, navigate to `/admin` login with `superuser`. And add some of the book objects that we created. 

5. Create the Views to tell the database how to display the book models.

    - go to `sample_app/views.py` in our app directory and create a generic view with the class `ListView`

    ```python
    # sample_app/views.py
    from django.views.generic import ListView

    from .models import Book


    class BookListView(ListView):
        model = Book
        template_name = "book_list.html"
    ```

6. Create our URLs so we have some logic that the user can interact with

    - go to our `project/urls.py` in our project's dir and configure the file.

        - import the path to the app using `path` and `include`. Configure the `sample_app.urls` as a path to be included in the `urlpatterns`

        ```python
        # django_project/urls.py
        from django.contrib import admin
        from django.urls import path, include  # new

        urlpatterns = [
        path("admin/", admin.site.urls),
        path("", include("sample_app.urls")),  # new
        ]
        ```

    - go to `sample_app/urls.py` and configure that file to use the view we created

    ```python
    # sample_app/urls.py
    from django.urls import path

    from .views import BookListView

    urlpatterns = [
        path("", BookListView.as_view(), name="home"),
    ]
    ```

7. Creating Template files to control the actual layout and output of the web page. 

    - create a new directory called `templates` inside the `sample_app` directory. And within that `templates` directory we want to include the `books` directory since we're dealing with book objects

    ```
    (.venv) > mkdir sample_app/templates
    (.venv) > mkdir sample_app/templates/books
    ```

    - can also be done at the root project dir.

    - now create the actual `.html` file inside of the template and fill in some basic django template language markdown

    ```html
    <!-- sample_app/templates/books/book_list.html -->
    <h1>All books</h1>
    {% for book in book_list %}
    <ul>
    <li>Title: {{ book.title }}</li>
    <li>Subtitle: {{ book.subtitle }}</li>
    <li>Author: {{ book.author }}</li>
    <li>ISBN: {{ book.isbn }}</li>
    </ul>
    {% endfor %}
    ```

8. Create our Test for the Book model, views, urls and templates.

    - go to our `tests.py` file that lives inside of our `sample_app` dir

    - import the Django class `TestCase` from django.test and `reverse` method from django.urls

    - also import the model that want to ultimately test in this case it would be `Book` from `.models`

    - Setup some dummy data and test that our model is created and being retrived with successful messages when we make a request to the view.

    ```python
    # sample_app/tests.py
    from django.test import TestCase
    from django.urls import reverse

    from .models import Book


    class BookTests(TestCase):
        @classmethod
        def setUpTestData(cls):
            cls.book = Book.objects.create(
                title="A good title",
                subtitle="An excellent subtitle",
                author="Tom Christie",
                isbn="1234567890123",
            )

        def test_book_content(self):
            self.assertEqual(self.book.title, "A good title")
            self.assertEqual(self.book.subtitle, "An excellent subtitle")
            self.assertEqual(self.book.author, "Tom Christie")
            self.assertEqual(self.book.isbn, "1234567890123")

        def test_book_listview(self):
            response = self.client.get(reverse("home"))
            self.assertEqual(response.status_code, 200)
            self.assertContains(response, "excellent subtitle")
            self.assertTemplateUsed(response, "books/book_list.html")
    ```

    - run our command `python manage.py test` when local server is not running

    ```
    (.venv) > python manage.py test
    ```


9. Push our project to Git

- create a `.gitignore` and add the `.venv/` to the file so our git push ignores all of the packages

```
$ touch .gitignore
```

```
# in .gitignore

.venv/

```

- record installed packages to a `requirements.txt` file using the command `pip freeze >`

```
$ pip freeze > requirements.txt
```

- ACP our project and all its changes

```
$ git add .
$ git commit -m 'push message'
$ git push origin main
```


## Can you explain the primary differences between Django and Django REST framework?

Django is a web framework for building full-stack web applications, while Django REST framework is an extension of Django that is specifically designed for building RESTful APIs.

- Serialization: Django has its own serialization system, while Django REST framework provides a more powerful and flexible serialization system that supports JSON, XML, and other formats.

- Views: Django has several built-in views for rendering HTML templates, while Django REST framework provides a set of generic views for handling common API actions, such as listing objects, creating objects, and retrieving objects.

- Authentication and permissions: Django has built-in authentication and permission systems for securing web applications, while Django REST framework provides a more powerful authentication and permission system specifically designed for RESTful APIs.

- Serializers: In Django, serializers are typically used to convert model instances to JSON or other formats. In Django REST framework, serializers are more powerful and can be used to validate input data, handle nested relationships, and more.

- Routing: Django has built-in URL routing that maps URLs to views, while Django REST framework provides its own router for mapping URLs to views specifically for handling API requests.

- Pagination: Django doesn't have built-in support for pagination, while Django REST framework provides several pagination classes that can be used to paginate large sets of data that is returned by an API.

## Things I want to know more about

- I want to know more about building the Docker Containers and when is it used in the real world

> References
>
>[A Beginner's Guide to Docker](https://wsvincent.com/beginners-guide-to-docker/)
>
>[Django for APIS - Chapter3: Libray Website](https://djangoforapis.com/library-website-and-api/)
>
>[Official Django REST Framework Tutorial - A Beginners Guide](https://learndjango.com/tutorials/official-django-rest-framework-tutorial-beginners)