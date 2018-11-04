# Python 3.7 Docker Alpine image with Pipenv

Usage:

Create a Pipenv file with you expected dependencies.

Locking a Pipenv file for usage using this image:

    docker run -it --rm -v ${pwd}:/app andreilhicas/pipenv:alpine pipenv lock

This command will generate a Pipfile.lock . A sample Pifile is provided with this repository to test Pipfile.lock creation

Example Dockerfile to run a python web application, same usage as kennethreitz/pipenv .

```yml
FROM andreilhicas/pipenv:alpine
COPY . /app
CMD python app.py
```

> Advantages to using this image over kennethreitz/pipenv (Size only) - `114MB` vs `1.03GB`

> Disadvantages - This is an alpine based version, based on official python3.7:alpine images and some python packages might not work as expected in alpine