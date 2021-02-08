# My First Django Project

This project is based on the Django Documentation - Writing your first Django app.

For more details, access the link https://docs.djangoproject.com/en/3.1/intro/tutorial01/

It’ll consist of two parts:

- A public site that lets people view polls and vote in them.
- An admin site that lets you add, change, and delete polls.


Steps:
## TUTORIAL PART I
1. Creating mysite directory in some current directory
django-admin startproject mysite

2. Running the app. In the outer mysite directory, hit the command in cmd prompt
py manage.py runserver

3. Creating the Polls app (To create your app, make sure you’re in the same directory as manage.py and type this command)
py manage.py startapp polls

- Projects vs. apps
An app is a Web application that does something.
A project is a collection of configuration and apps for a particular website.
A project can contain multiple apps.
An app can be in multiple projects.

4. Writing my first view
In polls/views.py write:

from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. You're at the polls index."

5. Maping the view to a URL and calling it:
Create a urls.py into polls directory

from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]

6. Including the new URLconf
    6.1. Import the include() function: from django.urls import include, path
    6.2. Add a URL to urlpatterns:  path('pools/', include('polls.urls'))

## TUTORIAL PART II
7. Making migrations according to INSTALLED_APPS in mysite/settings.py
py manage.py migrate

8. Creating the first model