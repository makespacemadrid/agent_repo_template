# Gobernanza de documentación

> Tier T2: crear cuando hay más de 1 agente o developer trabajando en el proyecto.
> Nota de plantilla: este documento define reglas reales, pero varios ejemplos del repositorio son ilustrativos hasta ser reemplazados por contexto del proyecto.

## Jerarquía de documentos

Si hay conflicto entre documentos, prevalece el orden superior:

1. **`AGENTS.md`** — Reglas globales para agentes
2. **`ROADMAP.md`** — Backlog priorizado y estado
3. **`docs/API_CONTRACT.md`** — Contratos backend/frontend activos
4. **`docs/WORKFLOWS.md`** — Flujos E2E canónicos
5. **`docs/KNOWN_GAPS.md`** — Deuda técnica y items diferidos
6. **`docs/HANDOFF.md`** — Continuidad entre sesiones

## Estados permitidos

| Estado | Significado |
|--------|-------------|
| `todo` | No iniciado |
| `in_progress` | En desarrollo activo |
| `done` | Implementado y validado |
| `deferred` | Pospuesto explícitamente |
| `blocked` | Bloqueado por dependencia o decisión |

## Reglas de actualización

Cada cambio funcional debe actualizar en el mismo PR/commit:
- Código fuente
- `ROADMAP.md` (estado del item)
- `docs/API_CONTRACT.md` (si endpoints o payloads cambiaron)
- `docs/KNOWN_GAPS.md` (si se abre o cierra deuda técnica)

No dejar estados ambiguos como "casi" o "parcial" sin una nota concreta.

## Definition of Done

Un item puede marcarse `done` solo si:
1. Build y tests relevantes pasan
2. Contrato API alineado (si aplica)
3. Documentación actualizada
4. Riesgos residuales explícitamente declarados

## Convención de ownership

En `ROADMAP.md` y/o `docs/HANDOFF.md`, usar:
- **owner**: agente o persona responsable
- **updated_at**: fecha ISO (`YYYY-MM-DD`)
- **evidence**: `ruta/archivo:línea`

## Regla de no-duplicación

- No crear otra fuente de verdad para el mismo tema.
- Si se necesita un resumen local, enlazar al documento canónico.
