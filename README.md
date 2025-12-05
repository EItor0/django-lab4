In this laboratory work, the Django web framework for Python was installed and explored. Django is a powerful and popular backend framework used for creating dynamic and scalable web applications.
The main goal of the lab was to install Django, create a new project and application, understand the MVT architecture, and display a simple static web page using an HTML template.

Installation:
1.Installing Python and Django:
Django was installed using the following command: pip install django
The installation was verified with: django-admin --version

2.Creating the Django Project:
A new Django project was created with: django-admin startproject myproject

3.Creating the Application:
Inside the new project folder, the application was created with: python manage.py startapp myapp
Django Architecture (MVT)

Django uses the MVT (Model–View–Template) architecture:
Model – manages database structure and data
View – contains the logic and returns a response
Template – handles the HTML layout shown to the user
Compared to the MVC pattern, Django’s View acts like the Controller because the framework itself handles much of the control flow internally.

Creating a Simple Static Web Page:

1.Adding the HTML Template
The static page created in Laboratory Work №3 (index.html) was placed inside: myapp/templates/myapp/index.html
At the top of the HTML file, static loading was enabled: {% load static %}

2.Adding CSS and Images
All CSS and image files were placed in: myapp/static/myapp/
The CSS file was connected in the template using: "<link rel="stylesheet" href="{% static 'myapp/styles.css' %}">"
Images were loaded with: "<img src="{% static 'myapp/breakfast.jpg' %}" alt="Breakfast">"

3.Creating the View
In myapp/views.py, the view that returns the HTML template was added:
from django.shortcuts import render

def index(request):
    return render(request, 'myapp/index.html')

4.Configuring URLs
In myproject/urls.py, the route was configured so that the page appears on the homepage:

from django.contrib import admin
from django.urls import path
from myapp import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', views.index, name='home'),
]

5.Running the Server
The development server was launched using: python manage.py runserver
The webpage successfully opened at: http://127.0.0.1:8000/

In conclusion:
During this laboratory work, Django was successfully installed and a project structure was created.
The MVT architecture was studied, and a static HTML page from the previous laboratory work was displayed using views, templates, and static files.
This provided practical understanding of how Django handles routing, templates, and static content.
