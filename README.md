# {{NOMBRE_PROYECTO}}

<!-- Breve descripción del proyecto (1-3 líneas) -->

## Prerrequisitos

- Docker ejecutándose localmente
- VS Code con la extensión "Dev Containers" instalada

## Arranque rápido

1. Abre la carpeta en VS Code.
2. Selecciona "Reopen in Container" (o `Dev Containers: Reopen in Container` desde la paleta).
3. Espera a que se construya el contenedor. Incluye: Node LTS + pnpm, Python 3.11 + pip, Git, Docker CLI.

## Trabajo con agentes de código

Este repositorio está preparado para colaboración con agentes de programación (Claude, Codex, Copilot, etc.):

- **`AGENTS.md`** — Fuente de verdad para todos los agentes. Lee este archivo primero.
- **`CLAUDE.md`** — Instrucciones específicas para Claude Code.
- **`ROADMAP.md`** — Backlog priorizado y foco actual.
- **`docs/`** — Documentación operacional (contratos API, workflows, handoffs, gaps, governance).

La estructura de `docs/` es progresiva: no necesitas todos los archivos desde el día 0. Consulta la tabla de tiers en `AGENTS.md` para saber cuándo crear cada documento.

## Archivos de configuración

| Archivo | Propósito |
|---------|-----------|
| `.devcontainer/devcontainer.json` | Imagen base, features (Node, Python, Git, Docker), extensiones VS Code |
| `.vscode/extensions.json` | Extensiones recomendadas (sincronizadas con devcontainer) |
| `.vscode/settings.json` | Format on save, terminal bash, final newlines |
