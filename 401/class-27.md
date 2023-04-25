# Django Models

## Explain the purpose and basic structure of Django models. How do they help in creating and managing database schema in a Django application?

The purpose of Django models is so that Django web applications can access and manage data through Python objects/models.

The Django models define the structure of the data that is being stored and a model should be created for every 'object' that we are potentially dealing with. We can define these models in our `models.py` file using the built in Django subclass `django.db.models.Model`. 

The basic structure of a Django model includes features such as:

- Class: This class will define a model, usually derived from the built in Model class.

```python
class MyModelName(models.Model):

```


- Fields: A model can have an arbitrary number of fields, of any type — each one represents a column of data that we want to store in one of our database tables. Each database record (row) will consist of one of each field value. This is also where you can assign the relationship type to other fields in other models. such as `OneToOneField`, `ForeignKey` (one to many) and `ManyToManyField`

```python

my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')

```

- Metadata: Declaares model-level metadata. Has many useful features such as ordering, verbose name, access permissions, etc. 

```python
class Meta:
    ordering = ['-my_field_name']

    verbose_name = 'BetterName'
```

- Methods: Gives the model functionality and the ability to have methods. Minimally, in every model you should define the standard Python class method `__str__()` to return a human-readable string for each object.

```python
def __str__(self):
    return self.my_field_name
```

Once a Django model is defined, it will allow us to create, update, delete, search and manage data through our web applications with Python code through Django and without ever touching a database. 


## Describe the primary features and functionality of the Django Admin interface. How can it be customized to suit the specific needs of a project?

The Django Admin interface is a built-in feature that allows developers to manage the data in their Django application via a web-based interface. The primary features of the Django Admin interface include the ability to create, read, update, and delete records in the application's database. It also provides a customizable user interface, user authentication, and permission management for different user roles.

The Django Admin interface can be customized to suit the specific needs of a project by modifying the built-in templates, creating custom views, and registering custom models. The built-in templates can be overridden by creating new templates with the same name and location in the project directory. 

Custom views can be added to the Admin interface by creating a new URL route and a corresponding view function. Custom models can be registered with the Admin interface by creating a new ModelAdmin class and registering it with the admin.site.register() function. Additionally, the Admin interface can be extended with third-party packages, such as Django Grappelli or Django Suit, to add additional functionality and styling options.

## Briefly outline the key components and workflow of a Django application, as discussed in the Beginner’s Guide to Django. How do these components interact with each other to create a functional web application?

The key components of a Django application include:

- Models: Django models define the data structure of the application, including the fields and relationships between different types of data.

- Views: Django views handle requests from clients and return responses, which can be HTML pages, JSON data, or other formats.

- Templates: Django templates define the structure and layout of HTML pages and can include dynamic content from views.

- URLs: Django URLs map incoming requests to the appropriate view function based on the URL pattern.

- Settings: Django settings contain configuration options for the application, such as database settings, installed apps, and middleware.

The workflow of a Django application typically involves the following steps:

- Define models: The developer defines the data models for the application, including the fields and relationships between different types of data.

- Create views: The developer creates view functions that handle incoming requests and return appropriate responses based on the data from the models.

- Define templates: The developer creates templates that define the structure and layout of HTML pages and can include dynamic content from views.

- Map URLs: The developer defines URL patterns that map incoming requests to the appropriate view function.

- Configure settings: The developer configures the Django settings to connect to the appropriate database, install any necessary apps, and configure middleware.

When a client sends a request to a Django application, the URL is matched to a URL pattern, which then calls the appropriate view function. The view function retrieves data from the models and passes it to the template, which then generates the HTML response that is sent back to the client. The components of the application interact with each other to create a functional web application by working together to retrieve, manipulate, and display data to the user.

### Things I want to know more about

- How exactly to query a database through Django or without ever 'touching' the database.

> References
>
>[Django Tutorial Part 3: Using models](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Models)
>
>[Django Tutorial: The Local Library website](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Tutorial_local_library_website)
>
>[Django Tutorial Part 4: Django admin site](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Admin_site)
>
>[A Complete Beginner's Guide to Django - Part 1](https://simpleisbetterthancomplex.com/series/2017/09/04/a-complete-beginners-guide-to-django-part-1.html)
>
>