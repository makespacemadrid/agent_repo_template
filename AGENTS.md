# Guía para agentes

Lee este archivo antes de modificar el repositorio. Para detalles complementarios específicos de Claude, revisa `CLAUDE.md` (no se duplican instrucciones entre ambos).

## Flujo de trabajo recomendado
- Trabaja siempre dentro del contenedor DevContainer o el espacio de trabajo de Coder para que las herramientas y extensiones estén disponibles.
- Mantén actualizados los archivos `CURRENT_PLAN.md` y `FOUND_WHILE_WORKING.md`:
  - Usa `CURRENT_PLAN.md` para anotar los pasos que ejecutarás antes de realizar cambios.
  - Usa `FOUND_WHILE_WORKING.md` para registrar hallazgos o pendientes detectados durante la ejecución.
- Prefiere comandos reproducibles; evita acciones manuales que no queden documentadas.
- Revisa los diffs antes de crear commits y evita cambios destructivos.

## Configuración de VS Code y extensiones
- Asegúrate de que las extensiones recomendadas en `.devcontainer/devcontainer.json` y `.vscode/extensions.json` se mantengan alineadas.
- La lista debe incluir asistentes de IA de OpenAI, Anthropic, Google, Qwen, Continue, SST OpenCode y las extensiones de Docker, Dev Containers y Coder remoto. Añade también herramientas de apoyo a Git como GitLens para facilitar la revisión del historial y trazabilidad de cambios.
- Si el proyecto usa Docker o Docker Compose, aprovecha la instancia local para correr pruebas reconstruyendo la imagen cuando sea necesario.
- Si el repositorio tiene GitHub Actions disponibles, utilízalas para compilar, ejecutar tests y distribuir imágenes cuando aplique.

## Documentación de cambios
- Si modificas configuraciones o documentación, explica brevemente el propósito para que otros agentes lo entiendan.
- Mantén la estructura de los archivos de configuración (JSON, Markdown) legible y con comentarios donde aplique.
- Si surge alguna duda sobre requisitos o expectativas, pregunta al usuario antes de asumir.
- No exfiltres información sensible o interna a repositorios externos.
