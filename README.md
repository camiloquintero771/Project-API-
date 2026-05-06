# [API-REST-EXAMPLE]

> "API REST para gestión de inventario en tiempo real, pensada para PYMES del sector retail."

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-4.2-092E20?logo=django&logoColor=white)](https://www.djangoproject.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15-336791?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Docker](https://img.shields.io/badge/Docker-24-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)

---

## 🎯 Contexto


- **Este proyecto fue creado como parte del aprendizaje autonomo en el manejo e implementación de APIS tipo REST.**

## ✨ Funcionalidades

- ✅ Funcionalidad 1 (ej: autenticación JWT)
- ✅ Funcionalidad 2 (ej: CRUD de productos con paginación)
- ✅ Funcionalidad 3 (ej: tareas asíncronas con Celery)
- 🚧 Funcionalidad pendiente

## 🧱 Stack técnico

- **Lenguaje:** Python 3.11
- **Framework:** Django + Django REST Framework
- **Base de datos:** PostgreSQL

## 🏗️ Arquitectura

> Si el proyecto lo amerita, agrega un diagrama (Mermaid funciona en GitHub):
>
> ```mermaid
> graph LR
>   Cliente -->|REST| Django
>   Django --> PostgreSQL
> ```

## ⚡ Quickstart

```bash
# 1. Clonar
git clone https://github.com/usuario/proyecto.git
cd proyecto

# 2. Configurar entorno
cp .env.example .env   # editar valores

# 3. Levantar
docker compose up -d --build

# 4. Migraciones y superuser
docker compose exec web python manage.py migrate
docker compose exec web python manage.py createsuperuser
```

API disponible en `http://localhost:8000`.

## 🔐 Variables de entorno

El proyecto usa un archivo `.env` para manejar la configuración. Nunca subas este archivo al repositorio — solo el `.env.example` con valores de referencia.

Copia el archivo de ejemplo y edita los valores según tu entorno:

```bash
cp .env.example .env
```

Estructura del `.env.example`:

```env
# Django
DEBUG=True
SECRET_KEY=change-me-generate-a-real-key
TZ=America/Bogota
DJANGO_SETTINGS_MODULE=config.settings
ALLOWED_HOSTS=localhost,127.0.0.1

# PostgreSQL
POSTGRES_DB=project_db
POSTGRES_USER=project_user
POSTGRES_PASSWORD=change-me-use-a-strong-password
POSTGRES_HOST=postgres
POSTGRES_PORT=5432
```

> 💡 Para generar un `SECRET_KEY` seguro:
> ```bash
> python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"
> ```

> ⚠️ **Importante:** asegúrate de que `.env` esté incluido en tu `.gitignore`. Solo el `.env.example` con placeholders debe estar versionado.

## 📡 Endpoints principales

| Método | Ruta | Descripción |
|--------|------|-------------|
| `POST` | `/api/auth/login/` | Obtener token JWT |
| `GET`  | `/api/products/` | Listar productos (paginado) |
| `POST` | `/api/products/` | Crear producto (auth) |

> Documentación interactiva: `http://localhost:8000/api/docs/`

## 🧪 Tests

```bash
docker compose exec web pytest --cov=apps
```

## 📂 Estructura del proyecto

```
.
├── apps/                  # Apps de Django (cada una una bounded context)
├── config/                # Settings, urls, asgi/wsgi
├── tests/                 # Tests de integración
├── docker-compose.yml
├── Dockerfile
├── pyproject.toml
└── README.md
```



## 👤 Autor

**Camilo Quintero** — Backend Developer
[LinkedIn](https://www.linkedin.com/in/camlo2021) · [GitHub](https://github.com/camiloquintero771) · quinterocamilo771@gmail.com


