# .NET 8 Catalog API

API REST mínima con **.NET 8**, **EF Core** y **PostgreSQL**, dockerizada y lista para probar.

## Correr con Docker
```bash
docker compose up -d
# Swagger: http://localhost:8080/swagger
```

## Endpoints
- `GET /api/products`
- `POST /api/products` body: `{ "id": 0, "name": "Item", "price": 10.5 }`
