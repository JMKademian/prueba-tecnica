Aplicación Django-React
Esta es una aplicación web que utiliza Django como backend y React como frontend. La aplicación se puede compilar y desplegar utilizando Docker y Docker Compose.

Requisitos
Antes de comenzar, asegúrese de tener instalados los siguientes programas en su máquina:

Docker
Docker Compose

Instrucciones para PC local
Clone este repositorio en su máquina local:
git clone https://github.com/username/django-react-app.git
Navegue hasta el directorio raíz del proyecto:
cd django-react-app
Cree un archivo .env en el directorio raíz del proyecto y defina las variables de entorno necesarias para la aplicación. Aquí hay un ejemplo de archivo .env:
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
DB_USER=postgres
DB_PASS=mysecretpassword
DB_HOST=db
DB_PORT=5432
Construya las imágenes de Docker para la aplicación de Django y la aplicación de React:
docker-compose build
Inicie los contenedores de Docker:
docker-compose up
Acceda a la aplicación de Django en su navegador web en http://localhost:8000 y a la aplicación de React en http://localhost:80.
Instrucciones para AWS
Cree una instancia de EC2 en AWS y asegúrese de tener acceso a ella.

Clone este repositorio en su máquina local:

git clone https://github.com/username/django-react-app.git
Navegue hasta el directorio raíz del proyecto:
cd django-react-app
Cree un archivo .env en el directorio raíz del proyecto y defina las variables de entorno necesarias para la aplicación. Aquí hay un ejemplo de archivo .env:
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
DB_USER=postgres
DB_PASS=mysecretpassword
DB_HOST=db
DB_PORT=5432
Cree una imagen de Docker para la aplicación de Django:
docker build -t django-app .
Cree una imagen de Docker para la aplicación de React:
docker build -t react-app -f frontend/Dockerfile .
Cree una imagen de Docker para la base de datos PostgreSQL:
docker build -t postgres -f db/Dockerfile .
Cree un volumen persistente para la base de datos:
docker volume create postgres_data
Inicie los contenedores de Docker utilizando Docker Compose:
docker-compose up -d
Acceda a la aplicación de Django en su navegador web utilizando la dirección IP pública de su instancia de EC2 y el puerto 8000 (http://<public-ip>:8000) y a la aplicación de React en el puerto 80 (http://<public-ip>).