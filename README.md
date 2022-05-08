A Django project test using Docker
===

This is a test project with Django.

Tree structure
========

```
├── README.md (this file)
├── docker-compose.yaml (general dockerfile description, aimed at development)
├── Dockerfile (General Dockerfile of the main server)
├── requirements.txt (python requirements)
├── environment.env (environment variables)
├── chapptest (project root)
│   └── chapptest (django root)
│       └── settings.py (django main settings file)
│       └── ...
│   └── chapp (main app)
├── manage.py
```

The code of the application is stored in `djangotest`, and docker-related files are in the root directory, docker-compose.yaml and Dockerfile.
These are the main docker files to operate at development.

The application includes some Django tests and a default connection to a Postgres database. The configuration of Django, including database 
connection is inside chapptest/settings.py

Docker services for development
=========

The main docker-compose file has all the services to run at development

Run a dev server that can be accessed at port 8000. It is using the django `runserver` command under the hood.

```
docker-compose up [-d]
```

In order to run the tests you need to run this Django command:

```
python manage.py test
```
