# Authentication & Production Server

## What is the primary purpose of JSON Web Tokens (JWTs) and how do they work in terms of encoding and decoding data?

The primary purpose of JSON Web Tokens (JWTs) are Authorization and Information Exchange:

- Authorization:
JWTs are used to authenticate and authorize users. When a user logs into a website or application, a JWT is created and returned to the client. This JWT can then be included in subsequent requests, allowing the server to verify the identity of the user and grant access to protected resources.

- Information Exchange:
JWTs can also be used to securely transmit information between parties. For example, a server might issue a JWT containing information about a user's shopping cart, which can then be transmitted to a third-party payment processor to complete a transaction.

To understand how JWTs work when it comes to encoding and decoding data we need to understand the three parts that they consist of:

- Header
The first part is the `header`. The header usually contains two parts, the type of token, `JWT`, and the algorithm used to sign it (HMAC, SHA265 or RSA are some example algorithms). Here's an example header:

```python
{
  "alg": "HS256",
  "typ": "JWT"
}

```

With this, our first part of the JWT is encoded in `Base64URL`

- Payload
The second part is the `payload`. This part contains the claims, or statements being made about an entity, like a user, and additional data. There are three types of claims (registered, public and private)

```python
{
  "sub": "1234567890",
  "name": "John Doe",
  "iat": 1516239022
}

```

This payload will be encoded as well, forming the second part of the JWT

- Signature
The signature is used to verify the integrity of the data. It is created by combining the header and payload, and signing the resulting string with a secret key that is known only to the server. Using the `HMAC SHA265` (`HS256`) algorithm our signature would look like this

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
```

- Decoding 
To decode the JWT, on the client-side, we need to split the JWT into its three parts and decode the header and payload. The signature is verified using the secret key (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

## How does JWT Authentication integrate with Django REST Framework to secure API endpoints, and what are the key components involved in this process?

JWT Authentication comes out of the box with the Django Rest Framework library. It can be implemented by exchanging a username and password for an access token and refresh token. 

The key components involved in this process are:

1. Installing Django Rest Framework and JWT

```
$ pip install djangorestframework
$ pip install djangorestframework-jwt
```

2. Configuring JWT in Django `settings.py` 

```python
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

3. Adding JWT views to the project directory's `urls.py` 

```python
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

4. Using DRF's `Response` and `permission_classes` in app directory's `views.py`
```python
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.permissions import IsAuthenticated


class HelloView(APIView):
    permission_classes = (IsAuthenticated,)

    def get(self, request):
        content = {'message': 'Hello, World!'}
        return Response(content)
```

5. Creating a path to the view in the app directory's `urls.py`

```python
from django.urls import path
from myapi.core import views

urlpatterns = [
    path('hello/', views.HelloView.as_view(), name='hello'),
]
```

## Why is Django’s built-in runserver not suitable for production environments, and what are some alternative server options that should be considered for deploying a Django application?

Django’s built-in `runserver` is a lightweight, single-threaded web server designed for development purposes. It’s not meant to handle high traffic or requests from multiple users simultaneously. Using runserver in a production environment can lead to a range of problems, including:

- Security vulnerabilities

- Poor performance

- Lack of scalability

- Limited configuration options

Some alternatives to using Django's built-in `runserver` are dedicated web servers such as: 

- Nginx

And a dedicated application server like:

- WSGI

- Gunicorn (an example of a WSGI server)


## Things I want to know more about

- Implementation of JWT in Django application, and if we ever have to create our own algorithms for JWTs or do they all come premade.


>References
>
>[JSON Web Tokens](https://jwt.io/introduction/)
>
>[DRF JWT Authentication](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)
>
>[Django Runserver Is Not Your Production Server](https://build.vsupalov.com/django-runserver-in-production/)
>
>[JWT with DRF](https://www.youtube.com/watch?v=Fhcn2qx-4VQ)
>
>[Gunicorn](https://gunicorn.org/)
>
>[Django Migrations Primer](https://realpython.com/django-migrations-a-primer/)