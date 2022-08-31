FROM python:3.9.5-slim-buster

WORKDIR /app

COPY . .

RUN apt-get update \
    && apt-get -y install libpq-dev gcc

RUN pip3 install -r requirements.txt

RUN python manage.py makemigrations
RUN python manage.py migrate
EXPOSE 8080

CMD ["python", "manage.py", "runserver"]
