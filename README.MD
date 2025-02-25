# Entorno de Desarrollo Docker con Portainer

Este proyecto configura un entorno de desarrollo local utilizando Docker Compose, que incluye Portainer para la gestión de contenedores y servicios esenciales como MySQL, PostgreSQL y Redis.

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

## Requisitos

* Docker y Docker Compose instalados en tu sistema.

## Cómo usar

1.  **Clona el repositorio:**

    ```bash
    git clone <tu_repositorio>
    cd <directorio_del_proyecto>
    ```

2.  **Levanta los contenedores:**

    ```bash
    docker compose up -d
    ```

3.  **Accede a Portainer:**

    * Abre tu navegador y ve a `https://localhost:9443`.
    * Sigue las instrucciones para configurar Portainer.

4.  **Accede a los servicios:**

    * **MySQL:** Conéctate utilizando un cliente MySQL al puerto 25060 con la contraseña `26QCDexGh7`.
    * **PostgreSQL:** Conéctate utilizando un cliente PostgreSQL al puerto 25061 con la contraseña `26QCDexGh7`.
    * **Redis:** Conéctate utilizando un cliente Redis al puerto 6379 con la contraseña `FeSBbMIywltp0LMdQcT9nStuZUosLxUVqwX2dJInvfc=`.

## Herramientas adicionales recomendadas

Considera agregar las siguientes herramientas para mejorar tu entorno de desarrollo:

* **pgAdmin (para PostgreSQL):**
    * Una interfaz gráfica para la gestión de bases de datos PostgreSQL.
    * Facilita la visualización y administración de bases de datos.
* **phpMyAdmin (para MySQL):**
    * Una interfaz gráfica para la gestión de bases de datos MySQL.
    * Facilita la visualización y administración de bases de datos.
* **Adminer:**
    * Alternativa ligera a phpMyAdmin, soporta MySQL, PostgreSQL, SQLite, entre otras.
* **RabbitMQ:**
    * Un broker de mensajes para la comunicación entre servicios.
    * Útil para arquitecturas basadas en microservicios.
* **MongoDB:**
    * Una base de datos NoSQL para aplicaciones que requieren flexibilidad y escalabilidad.
* **Traefik (o Nginx Proxy Manager):**
    * Un proxy inverso para gestionar el acceso a tus servicios.
    * Facilita la configuración de dominios y certificados SSL.
* **Mailhog:**
    * Un servidor de correo electrónico de prueba para capturar y visualizar correos electrónicos enviados por tus aplicaciones.
    * Útil para probar funcionalidades de envío de correos.
* **Elasticsearch/Kibana:**
    * Para logs y analisis de datos, muy util para microservicios.
* **Dockerized development enviroment:**
    * Contenedores dockerizados para los lenguajes de programacion que uses, esto ayuda a mantener homogeneo el ambiente de desarrollo.

## Consideraciones

* Asegúrate de cambiar las contraseñas predeterminadas por contraseñas seguras en un entorno de producción.
* Ajusta las configuraciones de los servicios según tus necesidades específicas.
* Asegurate de que tus microservicios esten conectados a la red development-network.

## Contribución

Las contribuciones son bienvenidas. Si tienes sugerencias o mejoras, no dudes en crear un pull request.