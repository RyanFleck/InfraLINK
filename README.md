[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/RyanFleck/Django-Deployable-Template/tree/master)

# Django-Deployable-Template
Django app with users and database, deployable on Heroku.

To run:
```sh
cd base
python3 manage.py runserver
```

To start a new app:
```
python3 manage.py startapp appname
```

Then add these to your new app:

urls.py
```py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

views.py
```py
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse("New web app.")
```

Add to base/urls.py
```py
urlpatterns = [
    path('', include('webapp.urls')),
    path('admin/', admin.site.urls),
]
```