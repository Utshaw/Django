# Django  ![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)

## Getting started
- Sometimes referred to as **MVC**
- Heavily influeneced by MVC
- Actually MTV (Model-Template-View)
- Model: Data access layer, anything to do with interacting, relating and validating data
- Template: presentation layer, presentation related decision
- View: Business logic layer. Access the model and displays the appropriate template
- Single project is thought to have multiple apps (abstract concept)
- `virtualenv` is recommended to use. (which is isolated environment)

## Installation and Run
1. Install python3 <br />
`sudo apt-get install python3`
2. Install pip <br />
`sudo apt-get install python3-pip`
3. Install virtual environment <br />
`sudo apt-get install python3-venv`
4. Create virtual environment <br />
`python3 -m venv env` 
5. Activate the virtual environment <br />
`source env/bin/activate`
6. Install Django <br />
`pip install django`
7. Create Django project <br />
`django-admin startproject <project_name>` # this will create <project_name> directory with `manage.py` and <project_name> file inside 
8. Enter inside the <project_name> folder and run `python manage.py runserver`
9. [MySQL] Install MySQL client from virtual environment in order to use MySQL `pip install mysqlclient` <br />
Troubleshooting:
Solve mysqlclient installation problem: `sudo apt install default-libmysqlclient-dev`
10. [MySQL] Change database name in <project_name>/settings.py:
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'utshawProject',
        'USER': 'root',
        'PASSWORD': '',
        'HOST': '127.0.0.1',
        'PORT': '3306'

    }
}
```
11. [ADMIN] Admin interface Link: http://127.0.0.1:8000/admin
12. [ADMIN] create superuser (access to the admin)
```
python manage.py createsuperuser --username=<name_here> --email=<email_here>
```
It will ask for new password and confirmation password

13. `python manage.py migrate` synchs django settings, apps and database with the project

14. Create app
```
python manage.py startapp <app_name> // python manage.py startapp products
```
This will create a directory with <app_name> with settings, models etc

 
## Django framework
### models.py
- Create app
```
python manage.py startapp <app_name> // python manage.py startapp products
```
This will create a directory with <app_name> with settings, models etc

**What to do after making changes in model** <br />
**BAD WAY** <br />
In order to modify the model of certain app and change datbase accordingly you need to do the following 
1. Delete everything from `migrations` folder inside the app folder
2. Delete `__pycache__` folder from inside the app folder 
3. Delete sqlite databse (db.sqlite3) [If that is used as storage] from project directory. If other datbase is used delete that. [Warning: It will delete all records]
4. Modify model as you want
5. Run these commands
```
python manage.py makemigrations
python manage.py migrate
```
**GOOD WAY**
1. Change what you need
2. Run these commands
```
python manage.py makemigrations
python manage.py migrate
```
3. Give a default value to anything which is creating the problem

### settings.py
- SECRET_KEY is unique key that must be private in production
- DEBUG must be set FALSE in production
- ALLOWED_HOSTS mean domain names that are allowed
- INSTALLED_APPS are like components (little pieces that make up the django project)
- MIDDLEWARE related to security feature
- ROUTE_URLCONF deals with routing
- TEMPLATES where HTML pages are stored
- DATABASES which databse is used by django
- AUTH_PASSWORD_VALIDATORS validates password 
- STATIC where I will store pictures and files
- `python manage.py migrate` synchs django settings, apps and database with the project

### admin.py
- Create Admin
```
python manage.py createsuperuser --username=<name_here> --email=<email_here>
```
- Add Admin access to certain models
```
from .models import *

admin.site.register(<Class_Name_1>)
admin.site.register(<Class_Name_2>)
admin.site.register(<Class_Name_3>)
```

### entering records
#### Using super user(Admin)
```
python manage.py createsuperuser --username=<name_here> --email=<email_here>
```
1. Go to http://127.0.0.1:8000/admin and go to app link and insert some records

#### Using Command line
```
python manage.py shell # opens shell program 
from sites.models import Site
Site.objects.create(firstParam='someParam', secondParam='someParam')
```

#### <app_name>/views.py
- Add custom html
```
def home_view(request, *args, **kwargs):
    return render(request, "home.html", {})
```
- Route to view from urls.py <br />
Add import statement <br />
```
from products.views import home_view
```
Add path to urlpatterns (this will replace default home page)
```
path('', home_view, name='home')
```



## Resources
### Django manual, documentation
- [Django field types](https://docs.djangoproject.com/en/2.2/ref/models/fields/)
### Django framework tutorial
- [Full course for beginners](https://youtu.be/F5mRW0jo-U4)
- [Traversy Media-YouTube](https://youtu.be/D6esTdOLXh4)
### Django installation guide
- [Installation on ubuntu](https://youtu.be/mqlCk_WCK2E)
