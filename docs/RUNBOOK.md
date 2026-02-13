# Runbook

> Tier T4: crear para el primer deploy. Referencia rápida de comandos operacionales.

## Desarrollo local

```bash
# Levantar servicios
docker compose up -d

# Ver logs
docker compose logs -f

# Parar servicios
docker compose down
```

## Testing

```bash
# Tests unitarios
docker compose run --rm app pytest

# Tests con coverage
docker compose run --rm app pytest --cov

# Lint
pnpm lint
```

## Build

```bash
docker compose build
```

## Deploy

<!-- Documentar proceso de deploy cuando exista -->

## Troubleshooting

<!-- Problemas comunes y soluciones -->
<!-- Ejemplo:
### Error: port already in use
```bash
lsof -i :8000
kill -9 <PID>
```
-->
