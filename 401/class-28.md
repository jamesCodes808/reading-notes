# Django CRUD and Forms

### How do Django Forms facilitate user input handling, and what are some key components of creating a form using the Django framework?

Django forms facilitate user input handling the same way that HTML forms do but in Django's case, the `view` gets a request, performs actions required such as reading data from the models, then it generates and returns an HTML page or refreshes the current page if a path isn't specified. Once this is all done the server processes the data that the user input and redisplays the page if there are any errors.

In steps this would go: 

1. Display the default form for the user.

2. Receive data from a submit request and bind it to the form

3. Clean and validate the data

4. If data invalid, re-display form with error messages

5. If data is valid, perform `required` actions

6. Once complete, redirect user to specified page.


Some of the key components for a Django form are:

- `forms.py` file inside of the application directory

- Declaring a `Form` class, using imported forms from django library as subclass

```python
from django import forms

class SampleForm(forms.Form):
    pass

```

- Form Fields, consists of different types of fields that derive from the `forms` library

```python

class SampleForm(forms.Form):
    email = forms.EmailField()

```

- Include arguments in the form fields when needed.

```python

class SampleForm(forms.Form):
    email = forms.EmailField(required=True)

```

- Validation, done on single fields when we override the method `clean_<fieldname>()`

```python
from django.core.exceptions import ValidationError
import re

class SampleForm(forms.Form):
    email = forms.EmailField(required=True)

    def clean_email(self):
        data = self.cleaned_data['email']

        # Check if email is valid
        if not re.search(r"^[A-Za-z0-9_!#$%&'*+\/=?`{|}~^.-]+@[A-Za-z0-9.-]+$", data):
            raise ValidationError(_('Invalid Email - Please enter a valid email'))
        
        # Always return the cleaned data
        return data
```

Another way to validate form fields is:

```python
from django.core import validators

class SampleForm(forms.Form):
    email = forms.EmailField(initial = 'Enter your email', required=True, validators=[validators.EmailValidator(message="Invalid Email")])

```

### Explain the purpose of Django Templates in web development and describe how template inheritance can be utilized to improve code reusability and maintainability.

Django Templates are used to create the HTML markup of a web page in a dynamic and reusable way. Templates are used to separate the presentation of the data from the business logic of the application, which makes it easier to maintain and update.

Template inheritance is a feature of Django templates that allows you to define a base template and then extend it in child templates. This can help you to reuse common HTML elements across your website, and make it easier to maintain your code.

Here is a simple example of how to use template inheritance in Django:

1. Define a base template that contains the common HTML elements you want to reuse across your website. In this example, we'll create a base template that includes a header and a footer:

```html
<!-- base.html -->
<html>
    <head>
        <title>{% block title %}{% endblock %}</title>
    </head>
    <body>
        <header>
            <h1>My Website</h1>
        </header>
        <div id="content">
            {% block content %}{% endblock %}
        </div>
        <footer>
            <p>Copyright &copy; 2023 My Website</p>
        </footer>
    </body>
</html>

```

2. In a child template, you can then extend the base template and override any blocks you need to customize. In this example, we'll create a child template that includes a custom title and some page-specific content:

```html
<!-- page.html -->
{% extends "base.html" %}

{% block title %}My Page{% endblock %}

{% block content %}
    <h2>Welcome to my page</h2>
    <p>This is some content specific to this page.</p>
{% endblock %}

```

When the child template is rendered, it will include all the HTML from the base template, with the blocks overridden as needed. This makes it easy to reuse common HTML elements across your website, while still allowing for customization for each page.


### Describe the function of Django Views in handling HTTP requests, and outline the differences between function-based views and class-based views.

In Django, Views are Python functions or classes that handle HTTP requests from the client and return an HTTP response. Views are the glue that connects the Model and Template components of the Django architecture, and they are responsible for processing data and rendering it in the appropriate format.

Function-based Views (FBVs) are simple Python functions that take a request object as input and return an HTTP response. Here's an example of an FBV that returns a simple "Hello, World!" message:

```python
from django.http import HttpResponse

def hello_world(request):
    return HttpResponse('Hello, World!')

```

Class-based Views (CBVs) are more powerful than FBVs and can provide additional functionality such as form handling and authentication. CBVs are defined as classes that inherit from Django's built-in View class or one of its subclasses. Here's an example of a CBV that displays a list of blog posts:

```python
from django.views.generic import ListView
from .models import Post

class PostListView(ListView):
    model = Post
    template_name = 'blog/post_list.html'

```

In the above example, the `PostListView` class extends Django's built-in `ListView` class and specifies the `model` and `template_name` attributes to display a list of `Post` objects using the `blog/post_list.html` template.

The main differences between FBVs and CBVs are that CBVs provide more functionality out-of-the-box and are easier to test and maintain in larger projects. However, FBVs can be more flexible and easier to understand for simple use cases.

In summary, Views are responsible for processing HTTP requests and returning HTTP responses in Django, and they can be implemented as either function-based or class-based. CBVs provide more functionality but can be more complex, while FBVs are simpler but more flexible.

## Things I want to know more about

- If we wanted different styles for different template pages, would we need to add a head to that page and compress a different CSS file? 


>References
>
>[Django Tutorial Part 9: Working with forms](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)
>
>[Django Tutorial Part 5: Creating our home page](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Home_page)
>
>[Django Tutorial Part 6: Generic list and detail views](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Generic_views)