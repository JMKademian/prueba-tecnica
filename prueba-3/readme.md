## PRUEBA 3

1. Utilizamos GitHub Actions como herramienta de CI/CD.
2. Crear el archivo Dockerfile que contenga las instrucciones para construir la imagen de nginx con el index.html default.
3. Crear el archivo .yml con el workflow que se encargará de construir y publicar la imagen de Docker en la plataforma elegida. En este archivo se deben especificar los siguientes elementos:
  -Nombre del workflow.
  -Evento que desencadena el workflow, en este caso, cada cambio realizado sobre el index.html.
  -Jobs que se deben ejecutar en el workflow.
  -Steps que se deben ejecutar en cada job.
4. Para que el workflow funcione correctamente, se deben definir los secretos necesarios en los ajustes del repositorio de GitHub. En este caso, se deben definir los secretos "DOCKER_USERNAME" y "DOCKER_PASSWORD" con las credenciales para autenticarse en la plataforma de Docker.
