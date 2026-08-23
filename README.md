# Django Backend Development with PostgreSQL

## Project Overview

This project is focused on learning and developing a production-oriented Django backend using PostgreSQL.

The main technologies used in the backend are:

- Python
- Django
- Django REST Framework
- PostgreSQL
- SQL
- Django ORM
- psycopg
- Git
- GitHub
- Environment Variables

The purpose of this project is to understand not only how to write Django code, but also how Django communicates with PostgreSQL, how models are converted into database tables, how migrations work, and how a production-oriented backend is structured.

---

# 1. Technology Stack

## Python

Python is the primary programming language used for backend development.

Python is used to write:

- Django configuration
- Models
- Views
- Business logic
- Database operations
- API logic
- Utility functions
- Tests

---

## Django

Django is a high-level Python web framework used to build secure, scalable, and maintainable web applications.

Django provides many built-in features:

- URL routing
- Views
- Models
- ORM
- Authentication
- Admin panel
- Middleware
- Sessions
- Forms
- Migrations
- Security features

---

## Django REST Framework

Django REST Framework (DRF) is used to build REST APIs with Django.

It provides features such as:

- Serializers
- API Views
- ViewSets
- Routers
- Authentication
- Permissions
- Validation
- Pagination
- API responses

---

## PostgreSQL

PostgreSQL is the relational database used by the application.

PostgreSQL stores structured data using:

- Databases
- Tables
- Rows
- Columns
- Primary Keys
- Foreign Keys
- Constraints
- Indexes
- Relationships

---

## psycopg

`psycopg` is the PostgreSQL adapter used by Python applications to communicate with PostgreSQL.

The communication architecture is:

    Django
       |
       v
    Django ORM
       |
       v
    PostgreSQL Backend
       |
       v
    psycopg
       |
       v
    PostgreSQL

---

## Git

Git is used for source-code version control.

It allows the project to maintain:

- Commit history
- Branches
- Code changes
- Rollbacks
- Collaboration

---

## GitHub

GitHub is used as the remote repository for the project.

The local Git repository can be connected to GitHub so that code can be pushed and stored remotely.

---

# 2. Development Environment

The project is developed on Windows using PowerShell.

Project directory:

    D:\Projects\django-fullstack

Virtual environment:

    D:\Projects\django-fullstack\venv

PostgreSQL configuration:

    Host     : 127.0.0.1
    Port     : 5432
    User     : postgres
    Database : django_interview

---

# 3. Git Setup

Git installation can be verified using:

    git --version

Configure Git username:

    git config --global user.name "Your Name"

Configure Git email:

    git config --global user.email "your-email@example.com"

Check Git configuration:

    git config --global --list

---

# 4. Initialize Git Repository

From the project root:

    git init

This creates a `.git` directory.

The `.git` directory contains Git repository information such as:

- Commit history
- Branch information
- Repository configuration
- Git objects
- Metadata

Check repository status:

    git status

---

# 5. Python Virtual Environment

A virtual environment provides an isolated Python environment for the project.

Without virtual environments, packages installed for different projects can conflict with each other.

For example:

    Project A
        |
        +-- Django 4.x

    Project B
        |
        +-- Django 5.x

Each project can have its own virtual environment and dependency versions.

---

# 6. Create Virtual Environment

Create the virtual environment:

    python -m venv venv

The command means:

    python
       |
       +-- -m
             |
             +-- venv module
                    |
                    +-- create environment named "venv"

The directory structure contains:

    venv/
    ├── Scripts/
    ├── Lib/
    └── ...

---

# 7. Activate Virtual Environment

On Windows PowerShell:

    .\venv\Scripts\Activate.ps1

After activation, the terminal displays something similar to:

    (venv) PS D:\Projects\django-fullstack>

The `(venv)` indicates that the virtual environment is active.

---

# 8. Why Use `python -m pip`

Packages can be installed using:

    pip install django

However, using:

    python -m pip install django

makes it clear that pip is being executed through the currently selected Python interpreter.

The flow is:

    Current Python
          |
          v
       python -m pip
          |
          v
    Current environment
          |
          v
    Install package

This is especially useful when multiple Python installations exist on Windows.

---

# 9. Django Installation

Install Django:

    python -m pip install django

Verify Django:

    python -m django --version

---

# 10. Django Installation Error

An error occurred:

    D:\Projects\django-fullstack\venv\Scripts\python.exe:
    No module named django

### Cause

The Python interpreter being used was inside the virtual environment, but Django had not been installed inside that environment.

### Solution

Activate the environment:

    .\venv\Scripts\Activate.ps1

Install Django:

    python -m pip install django

Verify:

    python -m django --version

### Important Concept

Packages installed globally are not automatically available inside a virtual environment.

---

# 11. `django-admin` vs `python -m django`

The command:

    django-admin --version

can fail with:

    django-admin : The term 'django-admin' is not recognized...

An alternative is:

    python -m django --version

This executes Django using the currently active Python interpreter.

For project-specific commands, Django provides:

    python manage.py <command>

Examples:

    python manage.py runserver
    python manage.py startapp users
    python manage.py makemigrations
    python manage.py migrate

---

# 12. PostgreSQL

PostgreSQL is a relational database management system.

A simplified database structure is:

    Database
       |
       +-- Table
             |
             +-- Columns
             |
             +-- Rows

Example:

    users
    --------------------------------
    id | name | email
    --------------------------------
    1  | John | john@example.com
    2  | Alex | alex@example.com

---

# 13. PostgreSQL Connection Information

The local PostgreSQL server uses:

    Host:
    127.0.0.1

    Port:
    5432

    User:
    postgres

    Database:
    django_interview

### Host

`127.0.0.1` represents the local computer.

### Port

`5432` is PostgreSQL's default port.

### User

`postgres` is the PostgreSQL database user.

### Database

`django_interview` is the database used by the Django project.

---

# 14. PostgreSQL `psql`

`psql` is PostgreSQL's command-line client.

Check PostgreSQL:

    psql --version

Connect to PostgreSQL:

    psql -U postgres

The command may ask for the PostgreSQL user's password.

---

# 15. PostgreSQL PATH Issue

The following error occurred:

    psql : The term 'psql' is not recognized...

### Meaning

Windows could not find the `psql` executable.

PostgreSQL executable files are located inside its `bin` directory.

The PostgreSQL `bin` directory needs to be added to the Windows PATH environment variable.

After PATH configuration:

    psql --version

can be executed from PowerShell.

### Important Concept

The PATH environment variable tells Windows where to search for executable commands.

---

# 16. Useful PostgreSQL Commands

List databases:

    \l

Connect to a database:

    \c django_interview

List tables:

    \dt

Exit PostgreSQL:

    \q

---

# 17. Create PostgreSQL Database

The Django configuration uses:

    django_interview

When Django attempted to connect, PostgreSQL returned:

    FATAL: database "django_interview" does not exist

This means the PostgreSQL server was accessible, but the requested database did not exist.

Create the database:

    CREATE DATABASE django_interview;

Verify databases:

    \l

Connect:

    \c django_interview

---

# 18. Understanding PostgreSQL Errors

There is an important difference between:

    Connection refused

and:

    Database does not exist

## Connection Refused

Example:

    connection to server at "127.0.0.1", port 5432 failed

Possible causes:

- PostgreSQL service is not running
- Incorrect host
- Incorrect port
- Network or firewall issue

Flow:

    Django
       |
       v
    PostgreSQL Server
       |
       X
    Connection Failed

---

## Database Does Not Exist

Example:

    FATAL: database "django_interview" does not exist

This means:

    Django
       |
       v
    PostgreSQL Server
       |
       v
    Connection successful
       |
       v
    Database not found

---

# 19. Create Django Project

The Django project was created using:

    python -m django startproject config .

The `.` is important because it tells Django to create the project in the current directory.

---

# 20. Django Project Structure

The basic project structure is:

    django-fullstack/
    │
    ├── config/
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   ├── asgi.py
    │   └── wsgi.py
    │
    ├── venv/
    │
    └── manage.py

---

# 21. `manage.py`

`manage.py` is Django's project command-line utility.

It is used for:

- Starting the development server
- Creating applications
- Creating migrations
- Applying migrations
- Creating superusers
- Opening Django shell
- Running tests

Examples:

    python manage.py runserver

    python manage.py startapp users

    python manage.py makemigrations

    python manage.py migrate

    python manage.py createsuperuser

    python manage.py shell

---

# 22. `settings.py`

Location:

    config/settings.py

This contains the main Django configuration.

Important settings include:

    SECRET_KEY
    DEBUG
    ALLOWED_HOSTS
    INSTALLED_APPS
    MIDDLEWARE
    DATABASES
    ROOT_URLCONF
    TEMPLATES
    WSGI_APPLICATION

The PostgreSQL database configuration is also defined here.

---

# 23. `urls.py`

Location:

    config/urls.py

Django uses URL configuration to map incoming HTTP requests to views.

Basic flow:

    HTTP Request
          |
          v
    URL Configuration
          |
          v
        View
          |
          v
      Response

For example:

    /api/users/
          |
          v
      Users View

---

# 24. WSGI

File:

    config/wsgi.py

WSGI stands for:

    Web Server Gateway Interface

It provides an interface between traditional Python web servers and Django applications.

Architecture:

    Web Server
         |
         v
       WSGI
         |
         v
      Django

---

# 25. ASGI

File:

    config/asgi.py

ASGI stands for:

    Asynchronous Server Gateway Interface

ASGI supports asynchronous Python web applications.

Architecture:

    Web Server
         |
         v
       ASGI
         |
         v
      Django

ASGI is useful for asynchronous functionality and technologies such as WebSockets.

---

# 26. Run Django Development Server

Start the server:

    python manage.py runserver

Default address:

    http://127.0.0.1:8000/

Stop the server:

    CTRL + C

The Django development server is intended for development and debugging, not production deployment.

---

# 27. Django Project vs Django App

This is an important Django concept.

## Django Project

The project contains the overall configuration of the Django application.

Example:

    config/

## Django App

An app contains functionality related to a particular business/domain area.

Example:

    users/

A project can contain multiple apps:

    Django Project
    │
    ├── users
    ├── products
    ├── orders
    └── payments

---

# 28. Create Django App

Create the users application:

    python manage.py startapp users

The application structure is:

    users/
    │
    ├── migrations/
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── models.py
    ├── tests.py
    └── views.py

---

# 29. Django App Files

## `models.py`

Defines database models.

Example:

    from django.db import models

    class UserProfile(models.Model):
        name = models.CharField(max_length=100)

Models are later converted into database tables through migrations.

---

## `views.py`

Contains request-handling logic.

Basic flow:

    Request
       |
       v
      View
       |
       v
    Business Logic
       |
       v
    Response

---

## `admin.py`

Used to configure models for the Django Admin panel.

---

## `apps.py`

Contains configuration for the Django application.

---

## `tests.py`

Used for automated tests.

---

## `migrations/`

Contains migration files generated by Django.

---

# 30. Django REST Framework

Install Django REST Framework:

    python -m pip install djangorestframework

DRF provides tools for developing REST APIs.

Important components include:

    Serializers
    API Views
    ViewSets
    Routers
    Authentication
    Permissions
    Validation
    Pagination

REST APIs commonly communicate using JSON.

Example response:

    {
        "id": 1,
        "name": "John",
        "email": "john@example.com"
    }

---

# 31. PostgreSQL Driver - psycopg

Install psycopg:

    python -m pip install "psycopg[binary]"

Django communicates with PostgreSQL through its database backend and PostgreSQL driver.

Architecture:

    Python Application
            |
            v
         Django
            |
            v
       Django ORM
            |
            v
    PostgreSQL Backend
            |
            v
          psycopg
            |
            v
       PostgreSQL

---

# 32. Environment Variables

Environment variables are used for configuration that should not be hard-coded.

A `.env` file can contain:

    SECRET_KEY=your-secret-key
    DEBUG=True

    DB_NAME=django_interview
    DB_USER=postgres
    DB_PASSWORD=your-password
    DB_HOST=127.0.0.1
    DB_PORT=5432

The actual password should not be committed to Git.

---

# 33. Why Use `.env`

Environment variables separate application code from environment-specific configuration.

For example:

Development:

    DB_NAME=django_interview_dev

Testing:

    DB_NAME=django_interview_test

Production:

    DB_NAME=production_database

The application code can remain the same while configuration changes between environments.

---

# 34. `.gitignore`

The `.gitignore` file prevents unnecessary or sensitive files from being committed to Git.

Typical entries:

    venv/
    .env
    __pycache__/
    *.pyc
    db.sqlite3

## `venv/`

The virtual environment contains installed dependencies and should normally not be committed.

## `.env`

May contain passwords and secret keys.

## `__pycache__/`

Contains Python-generated bytecode cache.

## `*.pyc`

Python compiled cache files.

---

# 35. Requirements File

Project dependencies can be stored in:

    requirements.txt

Generate the file:

    python -m pip freeze > requirements.txt

Install dependencies from the file:

    python -m pip install -r requirements.txt

This makes the development environment reproducible.

---

# 36. Django PostgreSQL Configuration

Django uses the `DATABASES` setting to configure database connectivity.

Example:

    DATABASES = {
        "default": {
            "ENGINE": "django.db.backends.postgresql",
            "NAME": os.getenv("DB_NAME"),
            "USER": os.getenv("DB_USER"),
            "PASSWORD": os.getenv("DB_PASSWORD"),
            "HOST": os.getenv("DB_HOST"),
            "PORT": os.getenv("DB_PORT"),
        }
    }

## `ENGINE`

Specifies the Django database backend.

    django.db.backends.postgresql

means PostgreSQL is being used.

## `NAME`

Database name:

    django_interview

## `USER`

PostgreSQL username.

## `PASSWORD`

PostgreSQL password.

## `HOST`

Database server address:

    127.0.0.1

## `PORT`

PostgreSQL port:

    5432

---

# 37. Django to PostgreSQL Connection Flow

The complete connection process is:

    .env
      |
      | Database credentials
      v
    settings.py
      |
      | DATABASES
      v
    Django Database Backend
      |
      v
    psycopg
      |
      v
    PostgreSQL Server
      |
      v
    django_interview

When Django performs a database operation:

    Python Code
        |
        v
    Django ORM
        |
        v
    SQL Query
        |
        v
    psycopg
        |
        v
    PostgreSQL

---

# 38. Django ORM

ORM stands for:

    Object Relational Mapper

Django ORM allows Python code to interact with relational databases using Python objects and QuerySets.

Example:

    User.objects.all()

Conceptually, Django generates SQL similar to:

    SELECT * FROM users_user;

The flow is:

    Python
       |
       v
    Django ORM
       |
       v
    SQL
       |
       v
    PostgreSQL

The ORM is one of the most important concepts in Django.

---

# 39. Django Models

A Django model represents the structure of data stored in the database.

Example:

    from django.db import models

    class UserProfile(models.Model):
        name = models.CharField(max_length=100)
        email = models.EmailField(unique=True)

Conceptually:

    Django Model
         |
         v
    Database Table

For example:

    UserProfile

may become a PostgreSQL table similar to:

    users_userprofile

The exact table name follows Django's naming rules unless explicitly configured.

---

# 40. Django Migrations

Django migrations provide a way to track database schema changes.

General workflow:

    models.py
        |
        v
    makemigrations
        |
        v
    Migration File
        |
        v
    migrate
        |
        v
    PostgreSQL

---

# 41. `makemigrations`

Command:

    python manage.py makemigrations

Purpose:

Detect changes in Django models and generate migration files describing those changes.

Example:

    users/migrations/
        0001_initial.py

The migration file contains instructions Django can use to modify the database schema.

---

# 42. `migrate`

Command:

    python manage.py migrate

Purpose:

Apply migration files to the configured database.

Flow:

    Migration File
         |
         v
    Django Migration System
         |
         v
    SQL Statements
         |
         v
    PostgreSQL

---

# 43. Difference Between `makemigrations` and `migrate`

| Command | Purpose |
|---|---|
| `makemigrations` | Creates migration files from model changes |
| `migrate` | Applies migration files to the database |

Example:

    Change models.py
          |
          v
    makemigrations
          |
          v
    Migration File
          |
          v
    migrate
          |
          v
    PostgreSQL schema updated

### Interview Answer

`makemigrations` detects changes in Django models and creates migration files, whereas `migrate` applies those migration files to the database.

---

# 44. Initial Django Migrations

The command:

    python manage.py migrate

applies Django's built-in migrations.

Django includes built-in applications such as:

    django.contrib.auth
    django.contrib.admin
    django.contrib.contenttypes
    django.contrib.sessions

These applications require database tables.

Therefore, the initial migration creates the tables required by Django itself.

---

# 45. Migration Tracking

Django keeps track of which migrations have already been applied.

View migrations:

    python manage.py showmigrations

Example:

    [X] contenttypes.0001_initial
    [X] auth.0001_initial
    [X] admin.0001_initial

`[X]` means the migration has been applied.

Django maintains migration history inside the database.

---

# 46. Database Schema

A database schema defines the structure of the database.

It includes:

- Tables
- Columns
- Data types
- Primary keys
- Foreign keys
- Constraints
- Indexes
- Relationships

Django models are used to define much of this structure from Python.

Flow:

    Python Model
         |
         v
    Migration
         |
         v
    Database Schema

---

# 47. Important Commands

## Git

    git --version
    git init
    git status
    git add .
    git commit -m "message"
    git push

---

## Python

    python --version
    python -m venv venv

---

## Virtual Environment

    .\venv\Scripts\Activate.ps1

---

## Package Installation

    python -m pip install django
    python -m pip install djangorestframework
    python -m pip install "psycopg[binary]"
    python -m pip install python-dotenv

---

## Dependency Management

    python -m pip freeze > requirements.txt

    python -m pip install -r requirements.txt

---

## Django

    python -m django --version

    python -m django startproject config .

    python manage.py runserver

    python manage.py startapp users

    python manage.py makemigrations

    python manage.py migrate

    python manage.py showmigrations

---

## PostgreSQL

    psql --version

    psql -U postgres

Inside `psql`:

    \l
    \c django_interview
    \dt
    \q

Create database:

    CREATE DATABASE django_interview;

---

# 48. Common Errors and Troubleshooting

## Error: `psql` is not recognized

Error:

    psql : The term 'psql' is not recognized...

Cause:

Windows cannot find the PostgreSQL executable.

Solution:

Add PostgreSQL's `bin` directory to the Windows PATH environment variable.

Verify:

    psql --version

---

# 49. Error: `django-admin` is not recognized

Use:

    python -m django --version

Also make sure the virtual environment is activated.

---

# 50. Error: `No module named django`

Check:

    python -m pip show django

If Django is not installed:

    python -m pip install django

---

# 51. Error: PostgreSQL Database Does Not Exist

Error:

    FATAL: database "django_interview" does not exist

Create the database:

    CREATE DATABASE django_interview;

---

# 52. Error: PostgreSQL Connection Refused

Example:

    connection to server at "127.0.0.1", port 5432 failed

Check:

1. PostgreSQL service is running.
2. Host is correct.
3. Port is correct.
4. PostgreSQL is listening on the configured port.
5. Database credentials are correct.

---

# 53. Backend Architecture

The basic Django backend request flow is:

    Client
       |
       | HTTP Request
       v
    Django URLs
       |
       v
    View
       |
       v
    Business Logic
       |
       v
    Django ORM
       |
       v
    SQL
       |
       v
    PostgreSQL
       |
       v
    Query Result
       |
       v
    View
       |
       v
    HTTP Response

Database communication:

    Django ORM
        |
        v
    Django Database Backend
        |
        v
    psycopg
        |
        v
    PostgreSQL

---

# 54. Interview Revision

## What is Django?

Django is a high-level Python web framework used to develop secure, maintainable, and scalable web applications.

---

## What is a Django project?

A Django project is the overall configuration and collection of applications that make up a Django application.

---

## What is a Django app?

A Django app is a modular component responsible for a particular functionality or business domain.

---

## What is Django ORM?

Django ORM is Django's Object Relational Mapper. It allows developers to interact with relational databases using Python objects and QuerySets instead of manually writing SQL for every database operation.

---

## What is PostgreSQL?

PostgreSQL is an open-source relational database management system that uses SQL.

---

## What is `psql`?

`psql` is PostgreSQL's command-line client used to interact with PostgreSQL databases.

---

## What is psycopg?

`psycopg` is a PostgreSQL adapter for Python that allows applications such as Django to communicate with PostgreSQL.

---

## What is a migration?

A migration is Django's mechanism for representing, tracking, and applying database schema changes.

---

## What does `makemigrations` do?

It detects changes in Django models and creates migration files.

---

## What does `migrate` do?

It applies migration files to the configured database.

---

## What is the difference between a model and a table?

A Django model is a Python representation of database structure.

A database table is the actual structure stored inside the relational database.

Conceptually:

    Django Model
         |
         v
    Migration
         |
         v
    PostgreSQL Table

---

## Why use a virtual environment?

A virtual environment isolates project dependencies and prevents dependency conflicts between projects.

---

## Why use environment variables?

Environment variables separate configuration from source code and protect sensitive information such as database passwords and secret keys.

---

## Why should `.env` not be committed to Git?

Because it can contain sensitive credentials and secret keys.

---

# 55. Core Architecture to Remember

The important relationship between the technologies is:

    Python
       |
       v
    Django
       |
       +----------------+
       |                |
       v                v
    Models            Views
       |
       v
    Django ORM
       |
       v
      SQL
       |
       v
    psycopg
       |
       v
    PostgreSQL

Django provides the application framework.

Models define database structures.

The ORM converts Python database operations into SQL.

The PostgreSQL backend and `psycopg` handle communication with PostgreSQL.

PostgreSQL executes the SQL and stores the data.

---

# 56. Learning and Interview Approach

For every Django concept, understand it at multiple levels:

    1. What is it?
           |
           v
    2. Why is it required?
           |
           v
    3. How is it implemented?
           |
           v
    4. How does Django handle it internally?
           |
           v
    5. What SQL is generated?
           |
           v
    6. How does PostgreSQL execute it?
           |
           v
    7. How is it used in production?
           |
           v
    8. What interview questions can be asked?

This approach focuses on practical understanding rather than only memorizing commands.

---

# 57. Quick Reference

Project:

    D:\Projects\django-fullstack

Virtual environment:

    D:\Projects\django-fullstack\venv

PostgreSQL:

    Host     : 127.0.0.1
    Port     : 5432
    User     : postgres
    Database : django_interview

Activate environment:

    .\venv\Scripts\Activate.ps1

Check Python:

    python --version

Check Django:

    python -m django --version

Run server:

    python manage.py runserver

Create migrations:

    python manage.py makemigrations

Apply migrations:

    python manage.py migrate

Check migrations:

    python manage.py showmigrations

Open PostgreSQL:

    psql -U postgres

Open Django shell:

    python manage.py shell

Install dependencies:

    python -m pip install -r requirements.txt

Save dependencies:

    python -m pip freeze > requirements.txt
