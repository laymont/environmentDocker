# Entorno de Desarrollo Docker con Portainer

Este proyecto configura un entorno de desarrollo local utilizando Docker Compose, que incluye Portainer para la gestión de contenedores y servicios esenciales como MySQL, PostgreSQL, Redis, MongoDB, RabbitMQ, Traefik, Mailhog y Elasticsearch/Kibana.

## Componentes

* **Portainer:**
    * Interfaz gráfica para la gestión de contenedores Docker.
    * Facilita la visualización y el control de los servicios en ejecución.
* **MySQL Server:**
    * Base de datos relacional MySQL para el almacenamiento de datos.
    * Configurado con una contraseña de root y zona horaria.
* **PostgreSQL Server:**
    * Base de datos relacional PostgreSQL para el almacenamiento de datos.
    * Configurado con una contraseña y zona horaria.
* **Redis Server:**
    * Almacén de datos en memoria Redis para caché y almacenamiento de datos temporales.
    * Configurado con una contraseña, persistencia y zona horaria.
* **MongoDB:**
    * Base de datos NoSQL para aplicaciones que requieren flexibilidad y escalabilidad.
* **RabbitMQ:**
    * Un broker de mensajes para la comunicación entre servicios.
    * Útil para arquitecturas basadas en microservicios.
* **Traefik:**
    * Un proxy inverso para gestionar el acceso a tus servicios.
    * Facilita la configuración de dominios y certificados SSL.
* **Mailhog:**
    * Un servidor de correo electrónico de prueba para capturar y visualizar correos electrónicos enviados por tus aplicaciones.
    * Útil para probar funcionalidades de envío de correos.
* **Elasticsearch/Kibana:**
    * Para logs y analisis de datos, muy util para microservicios.

## Requisitos

* Docker y Docker Compose instalados en tu sistema.

## Cómo usar

1.  **Clona el repositorio:**

    ```bash
    git clone <tu_repositorio>
    cd <directorio_del_proyecto>
    ```

2.  **Levanta los contenedores:**

    * **Archivo principal:** El archivo `docker-compose.yml` en la raíz del proyecto contiene la configuración inicial para Portainer, MySQL, PostgreSQL y Redis.

    * **Archivos adicionales:** Los archivos `docker-compose.mongodb.yml`, `docker-compose.rabbitmq.yml`, `docker-compose.traefik.yml`, `docker-compose.mailhog.yml` y `docker-compose.elk.yml` se encuentran en el directorio `addons/` y contienen la configuración para MongoDB, RabbitMQ, Traefik, Mailhog y Elasticsearch/Kibana, respectivamente.

    * **Levantar todos los servicios:** Para levantar todos los servicios, ejecuta el siguiente comando desde la raíz del proyecto:

        ```bash
        docker compose -f docker-compose.yml -f addons/docker-compose.mongodb.yml -f addons/docker-compose.rabbitmq.yml -f addons/docker-compose.traefik.yml -f addons/docker-compose.mailhog.yml -f addons/docker-compose.elk.yml up -d
        ```

    * **Levantar servicios específicos:** Para levantar servicios específicos, ejecuta el siguiente comando desde la raíz del proyecto:

        ```bash
        docker compose -f docker-compose.yml -f addons/docker-compose.nombre.yml up -d
        ```

        (Reemplaza `nombre` con el nombre del archivo `docker-compose` que deseas utilizar, por ejemplo, `mongodb` o `rabbitmq`).

3.  **Accede a Portainer:**

    * Abre tu navegador y ve a `https://localhost:9443`.
    * Sigue las instrucciones para configurar Portainer.

4.  **Accede a los servicios:**

    * **MySQL:** Conéctate utilizando un cliente MySQL al puerto 25060 con la contraseña `26QCDexGh7`.
    * **PostgreSQL:** Conéctate utilizando un cliente PostgreSQL al puerto 25061 con la contraseña `26QCDexGh7`.
    * **Redis:** Conéctate utilizando un cliente Redis al puerto 6379 con la contraseña `FeSBbMIywltp0LMdQcT9nStuZUosLxUVqwX2dJInvfc=`.
    * **MongoDB:** Conéctate utilizando un cliente MongoDB al puerto 27017 con el usuario `root` y la contraseña `26QCDexGh7`.
    * **RabbitMQ:** Accede a la interfaz de administración en `http://localhost:15672` con el usuario `guest` y la contraseña `26QCDexGh7`.
    * **Traefik:** Accede a la interfaz web en `http://localhost:8081` y a la API en `http://localhost:8082`.
    * **Mailhog:** Accede a la interfaz web en `http://localhost:8025`.
    * **Kibana:** Accede a la interfaz web en `http://localhost:5601`.

## Consideraciones

* Asegúrate de cambiar las contraseñas predeterminadas por contraseñas seguras en un entorno de producción.
* Ajusta las configuraciones de los servicios según tus necesidades específicas.
* Asegurate de que tus microservicios esten conectados a la red development-network.
* Recuerda que Traefik ocupara los puertos 80 y 443, por lo tanto, apache2 no funcionara en esos puertos.
* Elasticsearch y Kibana consumen muchos recursos, ajusta los limites de memoria segun tu hardware.

## Contribución

Las contribuciones son bienvenidas. Si tienes sugerencias o mejoras, no dudes en crear un pull request.