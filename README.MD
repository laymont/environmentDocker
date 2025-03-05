# Entorno de Desarrollo Docker con Portainer

Este proyecto configura un entorno de desarrollo local utilizando Docker Compose, e incluye Portainer para la gestión de contenedores junto con varios servicios esenciales: MySQL, PostgreSQL, Redis, MongoDB, RabbitMQ y Traefik.

## Componentes

- **Portainer:**  
  Interfaz gráfica para la gestión de contenedores Docker. Facilita la visualización y control de los servicios en ejecución.

- **MySQL Server:**  
  Base de datos relacional MySQL para el almacenamiento de datos, configurada con una contraseña de root y zona horaria.

- **PostgreSQL Server:**  
  Base de datos relacional PostgreSQL, configurada con una contraseña y zona horaria.

- **Redis Server:**  
  Almacén de datos en memoria Redis, utilizado para caché y almacenamiento de datos temporales, con configuración de contraseña, persistencia y zona horaria.

- **MongoDB:**  
  Base de datos NoSQL para aplicaciones que requieren flexibilidad y escalabilidad.

- **RabbitMQ:**  
  Broker de mensajes para la comunicación entre servicios, ideal para arquitecturas basadas en microservicios.

- **Traefik:**  
  Proxy inverso que gestiona el acceso a tus servicios, facilitando la configuración de dominios y certificados SSL.

- **Mailhog:**  
  Servidor de correo electrónico de prueba para capturar y visualizar los correos electrónicos enviados por tus aplicaciones.

## Requisitos

Asegúrate de tener Docker y Docker Compose instalados en tu sistema.

### Clonar el Repositorio

```bash
  git clone git@github.com:laymont/environmentDocker.git
  cd environmentDocker
```
### Defina las contraseña de los servicios
- MySQl: /mysql/.env
- Postgres: /postgres/.env
- Redis: /redis/.env
- Mongo: /mongo/.env
- RabbitMQ: /rabbitmq/.env

### Iniciar todos los servicios 

```bash
  docker compose -f addons/*/*.yml up -d
```
### Levantar servicios específicos

```bash
    docker compose -f docker-compose.yml -f addons/[nombre]/docker-compose.yml up -d
```

### Acceder a Portainer

- Abre tu navegador y navega a https://localhost:9443
- Sigue las instrucciones para configurar Portainer.

### Accede a los servicios
- MySQL: Conéctate a través de un cliente MySQL en el puerto 25060 con la contraseña [su-contraseña].
- Postgre: Conéctate a través de un cliente PostgreSQL en el puerto 25061 con la contraseña [su-contraseña].
- Redis: Conéctate a través de un cliente Redis en el puerto 6379 con la contraseña [su-contraseña].
- MongoDB: Conéctate a través de un cliente MongoDB en el puerto 27017 con el usuario root y la contraseña [su-contraseña].
- RabbitMQ: Accede a la interfaz de administración en http://localhost:15672 con el usuario guest y la contraseña [su-contraseña].
- Traefik: Accede a la interfaz web en http://localhost:8081 y a la API en http://localhost:8082.
- Mailhog: Accede a la interfaz web en http://localhost:8025.

## Consideraciones

- Cambia las contraseñas predeterminadas por contraseñas seguras en un entorno de producción.
- Ajusta las configuraciones de los servicios según tus necesidades.
- Asegúrate de que tus microservicios estén conectados a la red development-network.
- Recuerda que Traefik ocupa los puertos 80 y 443, por lo que Apache2 no podrá funcionar en esos puertos.
- Algunos servicios pueden consumir muchos recursos; ajusta los límites de memoria según tu hardware.

## Contribuciones
Las contribuciones son bienvenidas. Si tienes sugerencias o mejoras, no dudes en crear un pull request.


Si necesitas más modificaciones o tienes algún requerimiento adicional, no dudes en decírmelo.