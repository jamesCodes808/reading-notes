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

- `Form` class, when imported from django library

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

### Explain the purpose of Django Templates in web development and describe how template inheritance can be utilized to improve code reusability and maintainability.


### Describe the function of Django Views in handling HTTP requests, and outline the differences between function-based views and class-based views.

## Things I want to know more about

>References
>
>[Django Tutorial Part 9: Working with forms](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Forms)
>
>[Django Tutorial Part 5: Creating our home page](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Home_page)
>
>[Django Tutorial Part 6: Generic list and detail views](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Generic_views)