# codex_repo_template
Plantilla minima para trabajar con VS Code, devcontainers y agentes de programacion.

## Prerrequisitos
- Docker ejecutandose localmente.
- VS Code con la extension "Dev Containers" instalada.
- Acceso a las extensiones recomendadas para IA y trabajo remoto (Copilot, ChatGPT, Claude, Gemini, Qwen, Continue, OpenCode, Docker, Dev Containers y Coder remoto).

## Arranque rapido con devcontainer
1) Abre la carpeta en VS Code.  
2) Cuando se te pregunte, selecciona "Reopen in Container" (o `Dev Containers: Reopen in Container` desde la paleta).  
3) Espera a que se construya el contenedor. Se instalan Node LTS + pnpm, Python 3.11 + pip, Git y Docker CLI (con acceso al socket del host).

## Trabajo con agentes de programacion
- Dentro del contenedor se instalan extensiones de IA variadas (OpenAI, Anthropic, Google, Qwen, Continue y SST OpenCode) junto con Copilot; habilitalas en VS Code para autocompletado y chat contextual.
- El contenedor expone el socket de Docker, asi que puedes lanzar herramientas que requieran contenedores adicionales desde la terminal integrada.
- Usa la terminal de VS Code dentro del contenedor para ejecutar tus comandos (node, pnpm, python, pip, etc).
- Consulta `AGENTS.md` y `CLAUDE.md` para lineamientos de colaboracion entre agentes e incluye tu plan en `CURRENT_PLAN.md`; registra hallazgos en `FOUND_WHILE_WORKING.md`.
- Si trabajas con Docker o Docker Compose, puedes reconstruir y probar imágenes usando la instancia local expuesta en el devcontainer.
- Cuando existan flujos en GitHub Actions, apóyate en ellos para compilar, probar o distribuir imágenes en lugar de procesos manuales.

## Archivos de configuracion incluidos
- `.devcontainer/devcontainer.json` define la imagen base, caracteristicas (Node, Python, Git, Docker) y extensiones de VS Code.
- `.vscode/extensions.json` recomienda extensiones para contenedores, Docker y agentes de programacion.
- `.vscode/settings.json` activa formato al guardar y perfila la terminal bash.
