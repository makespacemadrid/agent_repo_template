# codex_repo_template
Plantilla minima para trabajar con VS Code, devcontainers y agentes de programacion.

## Prerrequisitos
- Docker ejecutandose localmente.
- VS Code con la extension "Dev Containers" instalada.
- Acceso a las extensiones recomendadas (Copilot y Copilot Chat) si quieres asistencia de IA.

## Arranque rapido con devcontainer
1) Abre la carpeta en VS Code.  
2) Cuando se te pregunte, selecciona "Reopen in Container" (o `Dev Containers: Reopen in Container` desde la paleta).  
3) Espera a que se construya el contenedor. Se instalan Node LTS + pnpm, Python 3.11 + pip, Git y Docker CLI (con acceso al socket del host).

## Trabajo con agentes de programacion
- Dentro del contenedor se instalan las extensiones recomendadas para trabajar con GitHub Copilot y Copilot Chat; habilitalas en VS Code para autocompletado y chat contextual.  
- El contenedor expone el socket de Docker, asi que puedes lanzar herramientas que requieran contenedores adicionales desde la terminal integrada.  
- Usa la terminal de VS Code dentro del contenedor para ejecutar tus comandos (node, pnpm, python, pip, etc).

## Archivos de configuracion incluidos
- `.devcontainer/devcontainer.json` define la imagen base, caracteristicas (Node, Python, Git, Docker) y extensiones de VS Code.
- `.vscode/extensions.json` recomienda extensiones para contenedores, Docker y agentes de programacion.
- `.vscode/settings.json` activa formato al guardar y perfila la terminal bash.
