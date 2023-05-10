## DIAGRAMA DE RED.

![image](https://github.com/JMKademian/prueba-tecnica/assets/96548645/0dd62d6d-ac51-4685-b0b5-546c3fc5d5dd)


1. Uiliza Virtual Private Cloud (VPC) con subredes en diferentes Availability Zones (AZ) para distribuir la aplicación web en múltiples data centers (Distintas regiones) y garantizar la disponibilidad y rebundancia en caso de fallos en alguno de ellos. Se le agrega el Internet Gateway que es un componente de AWS que permite la comunicación entre una red privada (como una VPC) y la internet pública.
2. Una instancia de Elastic Compute Cloud (EC2) para el frontend y configurarla para que se comunique con el backend(crear una para cada AZ). Agrego AWS Auto Scaling que le permite crear planes de escalado que automatizan la manera en la que diferentes recursos responden ante los cambios que se producen en la demanda con el objetivo de poder controlar la carga de tu aplicación.
3. Application Load Balancer (ALB) para distribuir la carga entre las instancias de EC2 y habilitar el escalado automático con grupos de escalado automático de AWS.
4. Cloudfront ya que agiliza la distribución de su contenido al dirigir cada solicitud de usuario mediante la red troncal de AWS a la ubicación de borde que mejor ofrezca su contenido, dirigda hacia el servicio bucket S3 que contiene el frontend. 
5. Utiliza una base de datos relacional en Amazon Relational Database Service (RDS) con alta disponibilidad que se comunica con el backend. Y una base de datos no relacional en Amazon DynamoDB y configurarla para que se comunique con el backend. La base de datos puede estar basada en documentos o en clave-valor, y puede utilizar AWS DynamoDB Streams para capturar los cambios en tiempo real 
6. Amazon API Gateway actúa como una capa intermedia que se comunica con las funciones Lambda del backend y que, a su vez, se comunican con las bases de datos. En otras palabras, Amazon API Gateway es el punto de entrada de las solicitudes de los usuarios hacia el backend de la aplicación web.
7. Dos funciones Lambda una por cada microservicio externo donde los datos de la solicitud se pasen correctamente a la función Lambda. 
