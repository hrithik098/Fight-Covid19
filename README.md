Health of India: Fight Covid19
==============================

An application to map symptomatic patients of covid19 on map and collect continuous health updates from individuals. Visit
[covid19.thepodnet.com](https://covid19.thepodnet.com).

![image](https://img.shields.io/badge/built%20with-Cookiecutter%20Django-ff69b4.svg)
![image](https://img.shields.io/badge/code%20style-black-000000.svg)

License
:   MIT

Setup
-----

1.  Clone the repository
    ```console
    $ git clone https://github.com/meticulousCraftman/Fight-Covid19
    ```

2.  Create a virtual environment using virtualenv or venv.
     ```console
     $ virtualenv -p python3 venv/ 
     $ source venv/bin/activate
     ```

3.  Install python packages
     ```console
     $ pip3 install -r requirements/local.txt
     ```

4.  Install OS dependencies (For linux systems only, others have to install it manually)
    ```console
    $ sudo ./utility/install\_os\_dependencies.sh install
    ```

5.  Setup Postgres database (assuming you have already installed it)
    ```console
    $ sudo -i -u postgres 
    $ createdb fight_covid19 
    $ createuser --interactive 
    Enter name of role to add: <username>
    Shall the new role be a superuser? (y/n) y
    ```

6.  Point django to the database instance. Create a .env file with the
    following content:
    ```env
    # These variables are used locally
    DATABASE_NAME=postgres:///fight_covid19 
    DATABASE_USER=apoorva
    DATABASE_PASSWORD=apple007 
    DATABASE_HOST=127.0.0.1 
    DATABASE_PORT=5432
    ```
    
    ```console
    $ touch .env
    $ nano .env
    <paste the contents of the file>
    ```
    
    
7.  Run project locally
    ```console
    $ python manage.py runserver
    ```

Todo
----

1.  Update this README docs to post instructions for installation
2.  Tasks to perform
3.  Optimizations to perform on database

Settings
--------

Moved to
[settings](http://cookiecutter-django.readthedocs.io/en/latest/settings.html).

Basic Commands
--------------

### Setting Up Your Users

-   To create a **normal user account**, just go to Sign Up and fill out
    the form. Once you submit it, you'll see a "Verify Your E-mail
    Address" page. Go to your console to see a simulated email
    verification message. Copy the link into your browser. Now the
    user's email should be verified and ready to go.
-   To create an **superuser account**, use this command:

        $ python manage.py createsuperuser

For convenience, you can keep your normal user logged in on Chrome and
your superuser logged in on Firefox (or similar), so that you can see
how the site behaves for both kinds of users.

### Type checks

Running type checks with mypy:

    $ mypy fight_covid19

### Test coverage

To run the tests, check your test coverage, and generate an HTML
coverage report:

    $ coverage run -m pytest
    $ coverage html
    $ open htmlcov/index.html

#### Running tests with py.test

    $ pytest

### Live reloading and Sass CSS compilation

Moved to [Live reloading and SASS
compilation](http://cookiecutter-django.readthedocs.io/en/latest/live-reloading-and-sass-compilation.html).

### Sentry

Sentry is an error logging aggregator service. You can sign up for a
free account at <https://sentry.io/signup/?code=cookiecutter> or
download and host it yourself. The system is setup with reasonable
defaults, including 404 logging and integration with the WSGI
application.

You must set the DSN url in production.

Deployment
----------

The following details how to deploy this application.
