# Contratos API

> Tier T1: crear cuando aparece el primer endpoint. Living document — actualizar con cada cambio de API.
> Nota de plantilla: el endpoint de ejemplo debajo es ilustrativo; no implica que exista una API real implementada.

## Endpoints

<!-- Documentar cada endpoint con el formato siguiente -->

### `GET /ejemplo`

- **Descripción**: —
- **Auth**: requerida / pública
- **Request**: —
- **Response** (`200`):
```json
{
  "id": "string",
  "name": "string"
}
```
- **Errores**: `401 Unauthorized`, `404 Not Found`

---

## Checklist de alineación

Antes de mergear cambios de API, verificar:
- [ ] Endpoint path coincide entre backend y frontend
- [ ] Nombres de campos coinciden (no aliases no documentados)
- [ ] Tipos de respuesta coinciden con los tipos del frontend
- [ ] Errores manejados en el frontend para cada status code documentado
