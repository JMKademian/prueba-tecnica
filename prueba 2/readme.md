# Aplicación Django-React
Esta es una aplicación web que utiliza Django como backend y React como frontend. La aplicación se puede compilar y desplegar utilizando Docker y Docker Compose.

## Requisitos
Antes de comenzar, asegúrese de tener instalados los siguientes programas en su máquina:

-Docker
-Docker Compose

## Instrucciones para PC local
1. Clone este repositorio en su máquina local:
```
git clone https://github.com/JMKademian/prueba-2.git
```
2. Navegue hasta el directorio raíz del proyecto:
```
cd prueba 2
```
3. Cree un archivo .env en el directorio raíz del proyecto y defina las variables de entorno necesarias para la aplicación. 
Aquí hay un ejemplo de archivo .env:
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
DB_USER=postgres
DB_PASS=mysecretpassword
DB_HOST=db
DB_PORT=5432
SECRET_KEY = joseka
```
4. Construya las imágenes de Docker para la aplicación de Django y la aplicación de React:
```
docker-compose build
```
5. Inicie los contenedores de Docker:
```
docker-compose up
```
6. Acceda a la aplicación de Django en su navegador web en http://localhost:8000 y a la aplicación de React en http://localhost:80.

## Instrucciones para AWS

Para correr la aplicación en AWS, siga los siguientes pasos:

1. Crea una instancia de Amazon EC2: Inicia sesión en la consola de AWS y crea una instancia de Amazon EC2. Asegúrate de elegir una AMI que sea compatible con Docker y tenga los puertos necesarios abiertos. También deberás seleccionar el tipo de instancia adecuado para tu aplicación, dependiendo de los recursos necesarios.

2. Conéctate a la instancia de EC2: Conéctate a la instancia de EC2 a través de SSH. Dependiendo del sistema operativo que estés utilizando, la forma de conectarse puede variar.

3. Clona el repositorio: Clona el repositorio que contiene los archivos de la aplicación en el directorio raíz de la instancia de EC2.

4. Instala Docker: Instala Docker en la instancia de EC2 utilizando el siguiente comando:

```
sudo yum install docker
```

5. Inicia Docker: Inicia el servicio de Docker utilizando el siguiente comando:

```
sudo service docker start
```

6. Actualiza el archivo `docker-compose.yml`: En el archivo `docker-compose.yml`, actualiza la configuración de la base de datos para que se conecte a la instancia de Amazon RDS que acabas de crear. Para hacer esto, debes modificar las siguientes líneas:

```
db:
  image: postgres
  environment:
    POSTGRES_USER: admin
    POSTGRES_PASSWORD: admin
    POSTGRES_DB: test_db
```

Debes reemplazar estas líneas con la siguiente configuración:

```
db:
  image: postgres
  environment:
    POSTGRES_USER: <nombre_de_usuario_de_la_base_de_datos>
    POSTGRES_PASSWORD: <contraseña_de_la_base_de_datos>
    POSTGRES_DB: <nombre_de_la_base_de_datos>
    DB_HOST: <endpoint_de_la_instancia_de_amazon_rds>
    DB_PORT: <puerto_de_la_instancia_de_amazon_rds>
```

7. Inicia los contenedores de Docker: Después de actualizar el archivo `docker-compose.yml`, inicia los contenedores de Docker utilizando el siguiente comando:

```
sudo docker-compose up
```

8. Accede a la aplicación: Una vez que se hayan construido y ejecutado los contenedores de Docker, la aplicación debería estar disponible en la dirección IP pública de tu instancia de EC2 y en el puerto especificado en el archivo `docker-compose.yml`. Accede a la aplicación desde un navegador web utilizando la dirección IP pública de la instancia de EC2 y el puerto especificado.

