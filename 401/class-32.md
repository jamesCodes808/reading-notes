# Permissions & Postgresql

## What are the key components and purpose of Django Rest Framework (DRF) permissions, and how do they help in securing an API?

Django Rest Framework (DRF) provides a variety of built-in permissions that can be used to secure your API by controlling access to different resources. Permissions are used to ensure that only authorized users can access certain parts of the API, and they help to protect against unauthorized access or misuse.

There are two key components to DRF permissions:

1. Permission Classes:  These are classes that define the logic for determining whether a user has permission to access a particular resource or not. Some built in useful permission classes are `IsAuthenticated`, `IsAdminUser`, and `AllowAny`. You can also create custom permissions by subclassing with the `BasePermission` class into a `has_permission()` method. Here is a quick example of a custom permissions class that allows access to users from a specific group:

```python
from rest_framework.permissions import BasePermission

class GroupPermission(BasePermission):
    def has_permission(self, request, view):
        allowed_groups = ['admin', 'staff']
        user_groups = request.user.groups.values_list('name', flat=True)
        return any(group in allowed_groups for group in user_groups)

```

2. Permission Checks: These are the checks that are performed on incoming requests to determine whether the user has the required permission or not. DRF provides two types of permission checks: `has_permission()` and `has_object_permission()`. The `has_permission()` method is used to check whether the user has permission to access a particular view, while the `has_object_permission()` method is used to check whether the user has permission to perform a particular action on an object. Here is an example of using `IsAuthenticated` permission class to require authentication for a view. 

```python
from rest_framework.views import APIView
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response

class MyView(APIView):
permission_classes = [IsAuthenticated]

def get(self, request):
    content = {'message': 'Hello, World!'}
    return Response(content)

```

DRF permissions provide a powerful way to secure your API by controlling access to different views and resources. 

## In SQL, what is the purpose of the SELECT statement, and how would you use it to retrieve all columns from a table called ‘employees’?

In SQL, our `SELECT` statements are like our `READ` methods in our `CRUD` methods. We can use the wildcard asterisk `*` to `SELECT` all columns from a table. 

```
SELECT * FROM employees
```

with python we can execute these SQL queries using the `sqlite3` library like this:

```python
import sqlite3

# Connects to the database
conn = sqlite3.connect('example.db')

# Creates a cursor object
cur = conn.cursor()

# Executes the SELECT statement
cur.execute("SELECT * FROM employees")

# Fetches all rows from the result set
rows = cur.fetchall()

# Displays the results
for row in rows:
    print(row)

# Closes the cursor and connection
cur.close()
conn.close()
```

## Can you explain the role of DRF Generic Views and provide examples of their usage in building a RESTful API?

In Django, views are responsible for processing incoming requests and returning HTTP responses, such as in the Django REST Framework views.

Just like in vanilla Django, DRF provides some generic views that can be used to quickly build a RESTful API. These views handle common tasks such as retrieving or updating objects, handling pagination, and providing authentication and authorization.

Some of the generic views to cover the basic `CRUD` methods and how to use them are:

1. ListAPIView:
Used to return a list of objects from a database model. We have to use a queryset and serializer_class attribute to handle the retrieval and serialization of the data.

```python
from rest_framework.generics import ListAPIView
from .models import Thing
from .serializers import ThingSerializer

class ThingList(ListAPIView):
    queryset = Thing.objects.all()
    serializer_class = ThingSerializer

```

2. RetrieveAPIView:
Used to return a single object from database model. Uses queryset and serializer_class attributes to handle the retrieval and serialization of the data.

```python
from rest_framework.generics import RetrieveAPIView
from .models import Thing
from .serializers import ThingSerializer

class ThingDetail(RetrieveAPIView):
    queryset = Thing.objects.all()
    serializer_class = ThingSerializer

```

3. CreateAPIView
Used to create a new object in database model. Only uses the serializer_class attribute to handle the validation and creation of that object.

```python
from rest_framework.generics import CreateAPIView
from .serializers import ThingSerializer

class ThingCreate(CreateAPIView):
    serializer_class = ThingSerializer

```

4. UpdateAPIView:
Used to update an existing object in the database model. Uses queryset and serializer_class attributes to handle the retrieval and serialization of the data.

```python
from rest_framework.generics import UpdateAPIView
from .models import Thing
from .serializers import ThingSerializer

class ThingUpdate(UpdateAPIView):
    queryset = Thing.objects.all()
    serializer_class = ThingSerializer

```

5. DestroyAPIView:
Deletes an existing object in the database model. Uses queryset and serializer_class attributes to handle the retrieval and serialization of the data.

```python
from rest_framework.generics import DestroyAPIView
from .models import Thing
from .serializers import ThingSerializer

class ThingDelete(DestroyAPIView):
    queryset = Thing.objects.all()
    serializer_class = ThingSerializer
```

>References
>
>[DRF Permissions](https://www.django-rest-framework.org/api-guide/permissions/)
>
>[SQL Prework](https://codefellows.github.io/common_curriculum/prework/SQL)
>
>[Classy Django REST](http://www.cdrf.co/)
>
>[DRF Generic Views](https://www.django-rest-framework.org/api-guide/generic-views/)