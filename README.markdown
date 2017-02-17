## Project Development Environment Setup

### Instructions for setting up on Mac OS X:
(optional) Feel free to set up a virtual env for the development setup

- Install Python, pip and Django 1.10.2
```
brew install python

sudo easy_install pip

sudo pip install Django

```
- Clone Repository
```
git clone git@github.com:basilkhan05/se-challenge-expenses.git
```
- Run Database Migrations
```
cd se-challenge-expenses

python manage.py migrate
```
- Run Development Sever
```
python manage.py runserver
```
- Checkout the application in action at http://localhost:8000/


## Application Architecture

The CSV upload and parser application was built in Django 1.10.2 with a sqlite3 database. Django's Model-View-Template (MVT) framework makes the application modular with separation of concerns. This applies not only to the UI and template of the application, but also to the Models and Views that were generated for the csv files uploaded and for the expense summaries.

This Modular design can help in the integration of this application/feature into a larger application or Wave's production app. Separating the helper functions and using packages such as csv.DictReader can also help modify the helper functions to parse any other csv format with different header titles that can be defined or chosen by the user via an Admin UI. 

The html templates were further split into larger components (header, navbar, sidebar, etc.) that can assist a front-end engineer to integrate a component or parts of a component into an existing front-end framework like React or Angular. Furthermore, when deploying this application, the static files, which are further split into their own folder, can be served over a CDN or an AWS S3 buckets in production.

The choice of a light weight relational database (sqlite3) was made to help in quick development setup time as well as the ability to use powerful SQL queries to extract and summarize expense information and other queries as the need arises. 

### Future feature considerations (not an exhaustive list):
- File type validation
- CSV Field Type Validation (for dates and amounts)
- 'Parsing Status' flag in the database to let the user know that the file is still being processed/parsed (for very large file sizes)
- Better memory handling when parsing very large file sizes
- Limit on File Upload Size
- Upload feature implemented as an API to get response from the server on upload and parsing status
- Implementation of UI elements for the above

### Credits:
- [Google Charts](https://developers.google.com/chart/)
- [Material Kit: Free Bootstrap Material Design UI Kit](https://www.creative-tim.com/product/material-kit)
- [Django Project](https://www.djangoproject.com/)
- [minimal-django-file-upload-example](https://github.com/axelpale/minimal-django-file-upload-example)
