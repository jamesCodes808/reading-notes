# Django Custom User

## What are the key benefits of using a Django Custom User Model, and how does it differ from the default Django User Model?

If you're working on a Django project, you might be wondering whether to use the default Django User model or create a custom User model. While the default User model works well for many projects, there are several benefits to creating a custom User model using Django's built-in authentication system.

One of the main benefits of using a custom User model is flexibility. With the default User model, you're limited to the fields and functionality provided by Django. But with a custom User model, you can create fields that are specific to your project and add functionality that is tailored to your needs. For example, if you're building an e-commerce site, you might want to add a field for a customer's billing address or shipping preferences.

Another benefit of using a custom User model is security. The default User model stores passwords in a format called MD5, which is considered to be insecure. However, if you create a custom User model, you can use a stronger hashing algorithm, such as bcrypt or Argon2, to store passwords securely. This is particularly important if your site handles sensitive data, such as financial information or personal details.

Overall, creating a custom User model can provide greater flexibility and security for your Django project. 

## Explain the process of creating and implementing a Custom User Model in Django, including the necessary changes to settings.py and the required model fields.

Here are the necessary steps needed to create and implement a custom user model in Django:

1. Create a new Django app for your custom User model, using the command below in the terminal:

```
python manage.py startapp accounts

```

2. In the `accounts` directory, create a new file called `models.py`, if it's not already there. Import `AbstractBaseUser`, `BaseUserManager`, and `PermissionsMixin` from Django's built-in authentication system.

```python
from django.contrib.auth.models import AbstractBaseUser, BaseUserManager, PermissionsMixin

```

3. Create a custom `UserManager` class that inherits from `BaseUserManager`. This class will handle the creation and management of User instances.

```python
class UserManager(BaseUserManager):
    def create_user(self, email, password=None, **extra_fields):
        if not email:
            raise ValueError('The Email field must be set')
        email = self.normalize_email(email)
        user = self.model(email=email, **extra_fields)
        user.set_password(password)
        user.save(using=self._db)
        return user

    def create_superuser(self, email, password=None, **extra_fields):
        extra_fields.setdefault('is_staff', True)
        extra_fields.setdefault('is_superuser', True)
        return self.create_user(email, password, **extra_fields)

```

4. Create a custom `User` model that inherits from `AbstractBaseUser` and `PermissionsMixin`. In the new `User` model, define the fields that you want to include. `is_active`, `is_admin` , `is_staff`, `is_superuser` are required when creating custom user model. `USERNAME_FIELD` is what the user will use to log in, create account with. `is_admin` is granted to users who can change things in the database. The line, `objects = UserManager()` is needed so the `UserManager` can manage the `User`. 

```python
class User(AbstractBaseUser, PermissionsMixin):
    email = models.EmailField(unique=True)
    username = models.CharField(max_length=30, unique=True)
    date_joined = models.DateTimeField(verbose_name='date joined', auto_now_add=True)
    is_admin = models.BooleanField(default=False)
    is_active = models.BooleanField(default=True)
    is_staff = models.BooleanField(default=False)
    is_superuser = models.BooleanField(default=False)

    USERNAME_FIELD = 'email'
    REQUIRED_FIELDS = ['username']

    objects = UserManager()

    def __str__(self):
        return self.email

    def has_perm(self, perm, obj=None):
        return self.is_admin

    def has_module_perms(self, app_label):
        return True

```

5. In the project's `settings.py` file, add the following lines to indicate the new User model and the location of the User manager:

```python
AUTH_USER_MODEL = 'accounts.User'

```

6. In any views, serializers or forms where you need to reference the User model, replace the import statement from from `django.contrib.auth.models import User` to `from django.contrib.auth import get_user_model` and replace `User` with `get_user_model()`.

## What is DjangoX and how does it complement or extend the functionality of Django? Provide an example use case for incorporating DjangoX in a project.

DjangoX is a third-party package that extends the functionality of Django by providing additional tools and features to make building web applications even easier. It includes several pre-built templates and layouts that you can use to create a responsive, modern website quickly. Some of the key features of DjangoX include authentication, user management, and contact forms.

Here is an example use case of using a pre-built home page template from DjangoX

1. Install DjangoX by running the following command in the terminal:

```
pip install django-x

```

2. In your Django project, add 'django_x' to the list of installed apps in the `settings.py` file:

```python
INSTALLED_APPS = [
    # ... other installed apps ...
    'django_x',
]

```

3. Create a new app for your website, using the command below in the terminal:

```
python manage.py startapp website

```

4. In the website directory, create a new file called `views.py`, if it is not already there. Import the `TemplateView` class from `django_x.views`, and create a new view that inherits from `TemplateView`. This view will render the homepage of the website:

```python
from django_x.views import TemplateView

class HomePageView(TemplateView):
    template_name = 'website/home.html'

```

5. In the website app directory, create a new file called `urls.py`, if it not already there. Import the `HomePageView` and add a new URL pattern that maps to the view:

```python
from django.urls import path
from .views import HomePageView

urlpatterns = [
    path('', HomePageView.as_view(), name='home'),
]

```

6. Create a new directory called `templates` in the root directory, and create a new file called `home.html`. Add some HTML code to the file to create the homepage of your website.

```html
<!-- templates/home.html -->

{% extends "django_x/base.html" %}

{% block title %}Home{% endblock %}

{% block content %}
  <div class="container">
    <div class="jumbotron">
      <h1>Welcome to my website!</h1>
      <p class="lead">This is a sample homepage created using DjangoX.</p>
    </div>
  </div>
{% endblock %}

```

And just like that, DjangoX, will provide a pre-built template and layout for the home page. There are also other tools for authentication and user management that come with DjangoX that make it easier to implement than it would in vanilla Django. 

>References
>
>[Django Best Practices: Custom User Model](https://learndjango.com/tutorials/django-custom-user-model)
>
>[DjangoX](https://github.com/wsvincent/djangox)
>
>[Creating a Custom User Model (Django)](https://www.youtube.com/watch?v=eCeRC7E8Z7Y&t=59s)
>
>[Substituting a custom User model](https://docs.djangoproject.com/en/3.0/topics/auth/customizing/#auth-custom-user)
