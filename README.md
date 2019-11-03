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

## Installation
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
- Anytime you change something in the models run these commands
```
python manage.py makemigrations
python manage.py migrate
```



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

## Resources
- [Full course for beginners](https://youtu.be/F5mRW0jo-U4)
- [Installation on ubuntu](https://youtu.be/mqlCk_WCK2E)
- [Traversy Media-YouTube](https://youtu.be/D6esTdOLXh4)
