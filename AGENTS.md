# {{NOMBRE_PROYECTO}}

> Lee este archivo antes de modificar el repositorio. Es la fuente de verdad para todos los agentes de código.
> **Estado actual de esta plantilla**: muchos contenidos de `README.md`, `ROADMAP.md` y `docs/` son ejemplos para mostrar formato de trabajo.
> Antes de ejecutar cambios funcionales, reemplaza placeholders y ejemplos por datos reales del proyecto/sesión.

## Stack

<!-- Reemplaza con tu stack real -->
- **Backend**: —
- **Frontend**: —
- **Base de datos**: —
- **Infra**: Docker, DevContainer

## Estructura del proyecto

```
├── AGENTS.md              # Este archivo (entry point para agentes)
├── CLAUDE.md              # Addenda específica de Claude Code
├── PRIVATE.md             # Contexto sensible local (gitignored, ver sección abajo)
├── README.md              # Overview para humanos
├── ROADMAP.md             # Backlog priorizado + foco actual
├── .gitignore             # Exclusiones de git (secretos, builds, IDE)
├── .dockerignore          # Exclusiones de Docker build (si aplica)
├── docs/
│   ├── GOVERNANCE.md      # Jerarquía de docs, DoD, reglas de actualización
│   ├── ARCHITECTURE.md    # Diseño del sistema + diagramas
│   ├── API_CONTRACT.md    # Contratos API (living doc)
│   ├── WORKFLOWS.md       # Flujos E2E canónicos
│   ├── KNOWN_GAPS.md      # Deuda técnica y gaps activos
│   ├── HANDOFF.md         # Log de handoff entre sesiones
│   ├── RUNBOOK.md         # Comandos operacionales (build/test/deploy)
│   ├── taxonomy.yaml      # Taxonomía de docs para filtrado por agente
│   ├── decisions/         # Architecture Decision Records
│   └── design/            # Design docs (proposals, specs)
├── .devcontainer/         # Configuración DevContainer
└── .vscode/               # Settings y extensiones recomendadas
```

## Comandos

<!-- Reemplaza con los comandos reales de tu proyecto -->
```bash
# Build
docker compose build

# Test
docker compose run --rm app pytest

# Lint
pnpm lint          # o: ruff check .

# Dev
docker compose up -d
```

## Convenciones de código

<!-- Adapta a tu stack y estilo -->
- Nombres de variables y funciones: `snake_case` (Python) / `camelCase` (JS/TS)
- Commits: mensajes concisos en imperativo, en inglés o español consistente
- Seguridad: valida inputs en fronteras del sistema (API, formularios), nunca confiar en datos externos sin sanitizar
- No commitear secretos (.env, credentials, tokens) — usa variables de entorno

## Documentación — cuándo leer qué

| Documento | Cuándo leer |
|-----------|-------------|
| `ROADMAP.md` | Para saber qué hacer a continuación |
| `docs/GOVERNANCE.md` | Reglas de coordinación entre agentes y developers |
| `docs/API_CONTRACT.md` | Al consumir o modificar endpoints |
| `docs/WORKFLOWS.md` | Al validar comportamiento end-to-end |
| `docs/KNOWN_GAPS.md` | Antes de empezar trabajo nuevo (evitar duplicar esfuerzo) |
| `docs/HANDOFF.md` | Al iniciar o terminar una sesión de trabajo |
| `docs/RUNBOOK.md` | Para comandos de build, test, deploy |
| `docs/ARCHITECTURE.md` | Para entender el diseño del sistema |
| `docs/decisions/` | Para entender decisiones arquitectónicas pasadas |

## Reglas de operación

1. **Single source of truth**: cada tema tiene UN documento autoritativo. No duplicar información entre archivos.
2. **Actualización atómica**: cada cambio funcional debe actualizar en el mismo commit: código + `ROADMAP.md` + docs afectados.
3. **Definition of Done**: un item está `done` solo si: tests green + API alineada (si aplica) + docs actualizados + riesgos explícitos.
4. **No asumir**: si hay ambigüedad en requisitos, pregunta al usuario antes de actuar.
5. **No destruir**: revisa diffs antes de commitear. Confirma acciones destructivas (borrar archivos, reset, force push).
6. **Seguridad**: ver sección dedicada abajo.

## Seguridad y datos sensibles

### Qué NO commitear nunca
- Secretos: API keys, tokens, contraseñas, certificados
- Archivos `.env` con valores reales (commitear `.env.example` con placeholders)
- Datos privados de infraestructura: IPs internas, hostnames de producción, puertos no públicos
- Credenciales de servicios, base de datos, o terceros

### .gitignore y .dockerignore
- Mantener `.gitignore` actualizado al añadir tecnologías, dependencias o herramientas. Si introduces un nuevo framework, IDE, o lenguaje, verifica que sus artefactos estén excluidos.
- Si el proyecto usa Docker, mantener `.dockerignore` alineado para evitar que secretos, docs de desarrollo o artefactos innecesarios entren en las imágenes.
- Antes de commitear, revisar `git status` para detectar archivos que no deberían trackearse.

### PRIVATE.md — contexto sensible para agentes
Si necesitas que los agentes conozcan datos sensibles del entorno (URLs internas, puertos, nombres de servicios, estructura de infra) sin publicarlos en el repo:
1. Crear `PRIVATE.md` en la raíz (ya está en `.gitignore`)
2. Escribir ahí el contexto que los agentes necesitan pero no puede ser público
3. Los agentes deben leer `PRIVATE.md` si existe, pero **nunca copiar su contenido a archivos trackeados**

Ejemplo de contenido:
```markdown
## Infra interna
- API producción: https://api.internal.example.com:8443
- DB staging: postgres://user:pass@db-staging.internal:5432/app
- Deploy key fingerprint: SHA256:abc123...

## Cuentas de servicio
- CI/CD: service-account@project.iam.example.com
```

## Foco actual

→ Ver `ROADMAP.md` sección **Current Focus**

## Creación progresiva de docs

No todos los archivos en `docs/` son necesarios desde el día 0. Créalos cuando el proyecto los necesite:

| Tier | Cuándo crear | Archivos |
|------|-------------|----------|
| **T0** | Día 0 | `AGENTS.md`, `CLAUDE.md`, `README.md`, `ROADMAP.md` |
| **T1** | Primer endpoint | `docs/API_CONTRACT.md` |
| **T2** | >1 agente o dev | `docs/GOVERNANCE.md`, `docs/HANDOFF.md` |
| **T3** | Sistema non-trivial | `docs/ARCHITECTURE.md`, `docs/WORKFLOWS.md`, `docs/KNOWN_GAPS.md` |
| **T4** | Primer deploy | `docs/RUNBOOK.md` |
| **T5** | Agentes especializados | `docs/taxonomy.yaml`, `docs/decisions/` |
