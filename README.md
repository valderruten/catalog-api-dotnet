# 🧩 Catalog API – .NET 8 + PostgreSQL + Docker

![.NET](https://img.shields.io/badge/.NET%208.0-blueviolet?style=for-the-badge&logo=dotnet)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

API REST minimalista desarrollada en **.NET 8** con **Entity Framework Core** y base de datos **PostgreSQL**, totalmente **dockerizada** y con soporte para **Swagger**, ideal como base para proyectos de microservicios o portfolios de backend.

---

## 🚀 Características principales

- 🧠 Arquitectura **Minimal API** en .NET 8  
- 🐘 Base de datos **PostgreSQL**  
- ⚙️ Contenedores con **Docker + Docker Compose**  
- 🧾 Documentación automática con **Swagger UI**  
- 🧩 Ejemplo de **CRUD completo (Productos)**  
- 💾 ORM con **Entity Framework Core**  
- 🔄 Listo para **CI/CD** con GitHub Actions  

---

## 🛠️ Tecnologías utilizadas

| Componente | Descripción |
|-------------|-------------|
| **.NET 8** | Framework principal del backend |
| **Entity Framework Core** | ORM para PostgreSQL |
| **PostgreSQL 16** | Base de datos relacional |
| **Docker Compose** | Orquestación de contenedores |
| **Swagger / Swashbuckle** | Documentación de endpoints |
| **GitHub Actions** | Integración continua (CI/CD) |

---

## 🧩 Estructura del proyecto

Catalog.Api/

├── Program.cs
├── AppDb.cs
├── Product.cs
├── appsettings.json
├── Dockerfile
├── docker-compose.yml
├── README.md
└── .gitignore


---

## ⚙️ Configuración y ejecución local

### 🔹 Requisitos previos
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [.NET SDK 8.0](https://dotnet.microsoft.com/download/dotnet/8.0)
- [Git](https://git-scm.com/downloads)

### 🔹 Clonar el repositorio
```bash
git clone https://github.com/cvalderruten/catalog-api-dotnet.git
cd catalog-api-dotnet
🔹 Levantar los contenedores
docker compose up -d
🔹 Verificar ejecución

Swagger UI 👉 http://localhost:8080/swagger

📦 Endpoints principales
Método	Endpoint	Descripción
GET	/api/products	Lista todos los productos
POST	/api/products	Crea un nuevo producto
GET	/api/products/{id}	Obtiene un producto por ID
DELETE	/api/products/{id}	Elimina un producto
Ejemplo de body para POST:
{
  "id": 0,
  "name": "Laptop ASUS Zenbook",
  "price": 2450.00
}

☁️ Despliegue en la nube (Render o AWS)
🔹 Opción 1 – Render.com

Sube el repo a GitHub.

En Render → New Web Service → selecciona el repo.

Configura:

Build Command: dotnet publish -c Release -o out

Start Command: dotnet out/Catalog.Api.dll

Agrega la variable de entorno:

ConnectionStrings__Postgres=Host=<tu-host>;Database=catalog;Username=<user>;Password=<pass>

🔹 Opción 2 – AWS Elastic Beanstalk
dotnet publish -c Release
eb init
eb create catalog-api-env
eb deploy

🔄 Pipeline de CI/CD (GitHub Actions)

Archivo .github/workflows/ci-dotnet.yml:

name: .NET API CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    - name: Setup .NET
      uses: actions/setup-dotnet@v4
      with:
        dotnet-version: '8.0.x'
    - name: Restore dependencies
      run: dotnet restore
    - name: Build
      run: dotnet build --no-restore
    - name: Test
      run: dotnet test --no-build --verbosity normal

🧠 Autor

Carlos Andrés Valderrutén Rodríguez
👨‍💻 Desarrollador Backend | .NET | NestJS | AWS | CI/CD
🌐 LinkedIn
 | GitHub

📜 Licencia

MIT License © 2025 Carlos Andrés Valderrutén
---



