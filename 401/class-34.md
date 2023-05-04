# API Deployment

## What are the key principles to follow when organizing and configuring Django settings for a project, according to the “Django Settings Best Practices” reading?

- Different Environments: 
Have specific settings for different environments such as local, dev, ci, qa, staging, production, etc. 

- Sensitive Data:
Keep `SECRET_KEY`, DB passwords and tokens for third-party APIs stored somewhere safe like in an .env.

- Sharing Settings Between Team Members:
Ensure that if working on a team to follow necessary procedures to adjust code and settings when adding in third-party apps and libraries into application. 

- Django Settings Is Python Code:
The `settings.py` in Django can integrate great things if done correctly but can also break an application if not configured right.


## How does the White Noise library contribute to the efficient serving of static files in a Django application, and what are the steps to integrate it into a project?

The WhiteNoise library allows serving static files directly from the Python application without relying on a separate web server, which can improve performance and simplify deployment.

The steps to implementing `WhiteNoise` into a Django app are quite simple:

1. Install

```
pip install whitenoise
```

2. Edit `settings.py` file

```python
INSTALLED_APPS = [
    #...
    "whitenoise",
    #...

]

MIDDLEWARE = [
    # ...
    "django.middleware.security.SecurityMiddleware",
    "whitenoise.middleware.WhiteNoiseMiddleware",
    # ...
]

# If using docker add
STATIC_ROOT = 'staticfiles'
```


3. Run command

```
$ python manage.py collectstatic

# if using docker container

$ docker compose run web python manage.py collectstatic

```


## What is the purpose of Cross-Origin Resource Sharing (CORS) in web applications, and how can it be implemented and configured in a Django project to control access to resources?

Cross-Origin Resource Sharing (CORS) is a security mechanism that allows web servers to control access to resources from different origins or domains, preventing malicious websites from accessing sensitive data or resources on other domains. 

In a Django project, CORS can be implemented using the Django CORS headers package, which provides middleware for adding CORS headers to HTTP responses and controlling access to resources based on various criteria such as origin, HTTP methods, and headers.

To use Django CORS headers:

1. Install the package using pip:

```
$ pip install django-cors-headers
```

2. Add the middleware to the `MIDDLEWARE` and `INTALLED_APPS` setting in your Django project's `settings.py` file:

```python
INSTALLED_APPS = [
...
'corsheaders',
...
]

MIDDLEWARE = [
    # ...
    'corsheaders.middleware.CorsMiddleware',
    'django.middleware.common.CommonMiddleware',
    # ...
]

```

3. Configure the CORS settings in the `settings.py` file, specifying the allowed origins, methods, headers, and other options:

```python
CORS_ORIGIN_ALLOW_ALL = False
CORS_ORIGIN_WHITELIST = [
    'http://example.com',
    'https://example.com',
]
CORS_ALLOW_METHODS = [
    'GET',
    'POST',
    'PUT',
    'PATCH',
    'DELETE',
    'OPTIONS'
]
CORS_ALLOW_HEADERS = [
    'accept',
    'accept-encoding',
    'authorization',
    'content-type',
    'dnt',
    'origin',
    'user-agent',
    'x-csrftoken',
    'x-requested-with'
]


```

4. Apply the CORS headers to your `views.py` or entire Django application by using the `@corsheaders.decorators.cors_headers` decorator, as shown in this example view:

```python
from django.http import JsonResponse
from corsheaders.decorators import cors_headers

@cors_headers()
def my_view(request):
    data = {'message': 'Hello, World!'}
    return JsonResponse(data)

```

## Things I want to know more about

- I wonder what the difference is between using django built in authorization, JWT and CORS. It seems like a lot of different security measures. Do they all work together or are we supposed to choose between them as developers? 

>References
>
>[Configuring Django Settings: Best Practices](https://djangostars.com/blog/configuring-django-settings-best-practices/)
>
>[White Noise](http://whitenoise.evans.io/en/stable/)
>
>[CORS](https://en.m.wikipedia.org/wiki/Cross-origin_resource_sharing)
>
>[Django CORS Guide:What It Is and How to Enable It](https://www.stackhawk.com/blog/django-cors-guide/)
