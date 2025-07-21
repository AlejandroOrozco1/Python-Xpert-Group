FastAPI Technical Test with MongoDB (Dockerized)

Este proyecto es una prueba técnica basada en FastAPI y MongoDB, totalmente dockerizada para facilitar la ejecución en cualquier entorno. También se incluye el consumo de una API externa de gatos (TheCatAPI).

🌐 Tecnologías utilizadas

Python 3.11 (Alpine)

FastAPI

MongoDB 6.0 (Docker)

Beanie ODM

TheCatAPI

Docker & Docker Compose

📁 Estructura del proyecto

.
├── app/
│   ├── api/
│   │   └── api_v1/
│   │       ├── handlers/
│   │       │   ├── user_handler.py
│   │       │   └── cat_handler.py
│   ├── core/
│   │   ├── config.py
│   │   ├── database.py
│   │   └── security.py
│   ├── models/
│   │   └── user_model.py
│   ├── schemas/
│   │   ├── user_schema.py
│   │   ├── auth_schema.py
│   │   └── cat_schema.py
│   ├── services/
│   │   ├── user_service.py
│   │   └── cat_service.py
│   └── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── .env
└── README.md

Estructura del proyecto
app/: carpeta principal de la aplicación.

api/api_v1/handlers/: contiene los routers y controladores HTTP (como user_handler.py y cat_handler.py).

core/: configuración, conexión a MongoDB y seguridad (config.py, database.py, security.py).

models/: definición de modelos de datos con Beanie ODM (ej. user_model.py).

schemas/: esquemas Pydantic para validación de entradas y salidas (ej. user_schema.py, auth_schema.py, cat_schema.py).

services/: lógica de negocio separada por dominio (user_service.py, cat_service.py).

app.py: punto de entrada de la aplicación FastAPI.

.env: configuración de entorno como conexión a MongoDB y llaves JWT.

requirements.txt: dependencias del proyecto.

Dockerfile: define la imagen para construir el entorno de ejecución en contenedor.

docker-compose.yml: orquesta los servicios (MongoDB y la API).

README.md: documentación del proyecto.

Metodologías y buenas prácticas
Separación de responsabilidades: cada carpeta tiene una única función específica.

Inspiración en Clean Architecture: división clara entre controladores, lógica de negocio, modelos y configuración.

Uso de Docker para crear entornos consistentes, portables y sin dependencias del sistema host.

API First: endpoints bien definidos y centralizados por versión (api_v1).

Seguridad básica integrada con hashing de contraseñas y JWTs.

Uso de variables de entorno para mantener configuraciones desacopladas del código.


🚀 Ejecución del proyecto (modo Docker)

1. Requisitos previos

Tener instalado Docker y Docker Compose

2. Construir y levantar los contenedores

docker compose build
docker compose up

Esto levanta:

api en http://localhost:8000

mongo en localhost:27017

📚 Acceso a la documentación automática (Swagger y OpenAPI)
FastAPI genera automáticamente documentación interactiva para la API, accesible desde el navegador:

Swagger UI (interfaz interactiva para probar los endpoints):

http://localhost:8000/docs

OpenAPI Schema (especificación completa en formato JSON):

http://localhost:8000/openapi.json

Puedes usar estos enlaces mientras el contenedor esté en ejecución. Swagger permite enviar peticiones directamente desde la interfaz web y ver respuestas en tiempo real.