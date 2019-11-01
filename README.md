# Django 

## Idea
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
`django-admin startproject <project_name_here>` # this will create <project_name_here> directory with `manage.py` and <project_name_here> file inside 
8. Enter inside the <project_name_here> folder and run `python manage.py runserver`
 




## Resources
- [Installation on ubuntu](https://youtu.be/mqlCk_WCK2E)
- [Traversy Media-YouTube](https://youtu.be/D6esTdOLXh4)
