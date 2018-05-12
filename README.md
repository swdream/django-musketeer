# Django Muskerteer

Setting up a Django project basically using postgresql database.
Replace your app name and configuration values as you want.

## How to use

### 1. Create your virtualenv

```
$ mkdir your_app
$ cd your_app
$ virtualenv --python=python3 --no-site-packages env
```

### 2. Clone django-mustketeer

```
git clone git@github.com:swdream/django-musketeer.git
```

### 3. Activate your virtualenv and installing required packages

```
$ cd django-muskerteer
$ pip install -r requirements.txt
```

### 4. Setting up your database

```
sudo apt-get update
sudo apt-get install -y python-pip python-dev libpq-dev postgresql postgresql-contrib

sudo su - postgres
psql

CREATE DATABASE musketeer;
CREATE USER musketeer WITH PASSWORD 'musketeer';

ALTER ROLE musketeer SET client_encoding TO 'utf8';
ALTER ROLE musketeer SET default_transaction_isolation TO 'read committed';
ALTER ROLE musketeer SET timezone TO 'UTC';

GRANT ALL PRIVILEGES ON DATABASE musketeer TO musketeer;
```

In setting:

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'musketeer',
        'USER': 'musketeer',
        'PASSWORD': 'musketeer',
        'HOST': 'localhost',
        'PORT': '5432',
     }
 }
```

Migrate db:

```
python manage.py makemigrations
python manage.py migrate
```

Good luck and have a nice day. Thanks
