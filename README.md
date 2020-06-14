


The 2nd Django project will be building a complete blog. Django provides a command that allows you to create an initial project fle structure. Run the following command from your shell:
```
django-admin startproject mysite
```

You will create a blog application from scratch. From the project's root directory, run the following command:
```
python manage.py startapp blog
```

## Model Design
First, you need to defne a Post model. Add the following lines to the models.py file of the blog application:

## Activating the application
In order for Django to keep track of your application and be able to create database tables for its models, you have to activate it. To do this, edit the settings.py fle and add blog.apps.BlogConfig to the INSTALLED_APPS setting. 
It should look like this:
```
INSTALLED_APPS = [
	'django.contrib.admin',
	'django.contrib.auth',
	'django.contrib.contenttypes',
	'django.contrib.sessions',
	'django.contrib.messages',
	'django.contrib.staticfiles',
	'blog.apps.BlogConfig',
]
```

The BlogConfig class is your application confguration. Now Django knows that
your application is active for this project and will be able to load its models.

```
python manage.py makemigrations blog
```

Let's take a look at the SQL code that Django will execute in the database to create the table for your model. 
The sqlmigrate command takes the migration names and returns their SQL without executing it. Run the following command to inspect the SQL output of your frst migration:

```
python manage.py sqlmigrate blog 0001
```

Let's sync your database with the new model. Run the following command to apply existing migrations:

```
python manage.py migrate
```

## Creating a superuser
First, you will need to create a user to manage the administration site. Run the following command:

```
python manage.py createsuperuser
```

user name: admin
e-mail: astrid.wang1229@gmail.com
password: 123456

