# Django LAB

## Environments
### Create application - Init setup
#### Dockerfile for initializing setup
```

FROM python:3.11
LABEL maintainer="Quan Do Minh"

ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt /tmp/requirements.txt

COPY ./mysite /mysite
WORKDIR /mysite
EXPOSE 8000

RUN python -m venv /py && \
    /py/bin/pip install --upgrade pip && \
    /py/bin/pip install -r /tmp/requirements.txt && \
    rm -rf /tmp && \
    adduser \
        --disabled-password \
        --no-create-home \
        django-user

ENV PATH="/py/bin:$PATH"

USER django-user

```

#### Create project / app by docker-compose

```


## Using docker-compose to create superuser
docker-compose run --rm django_4sample_chapters_01 sh -c "python manage.py createsuperuser"


```

#### environment

```
_dev.env

DB_NAME=dbname
DB_USER=rootuser
DB_PASS=changeme
DJANGO_SECRET_KEY=changeme
DJANGO_ALLOWED_HOSTS=127.0.0.1
AUTHORIZE_MEDC=
MEDC_URL=

```


#### Developer

```
# Running containers
docker-compose up


```


#### Production




