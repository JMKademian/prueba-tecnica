FROM python:3.8

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt-get update

RUN apt-get install -y graphviz-dev

RUN apt-get install -y pkg-config

RUN apt-get install -y postgresql-contrib libpq-dev gcc python3-dev

WORKDIR /app/backend

COPY . .

COPY requirements.txt /app/backend

RUN python -m pip install --upgrade pip

RUN pip install -r requirements.txt

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
