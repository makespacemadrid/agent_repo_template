# {{NOMBRE_PROYECTO}} — Claude Code

Lee `AGENTS.md` para las reglas generales del proyecto. Aquí solo se añaden instrucciones específicas para Claude Code.

## Instrucciones Claude-specific

- Si existe `PRIVATE.md`, léelo al inicio de la sesión para contexto sensible del entorno. Nunca copies su contenido a archivos trackeados por git.
- Usa tono conciso en archivos compartidos. Deja claro el contexto y motivos de cada cambio.
- Si hay dudas sobre requisitos, pregunta al usuario — no inferir.
- Usa Docker local para reconstruir imágenes y probar antes de proponer cambios.
- Ejecuta GitHub Actions cuando existan para build/test/distribute en vez de pasos manuales.
- No copies ni exportes información sensible fuera del repositorio.

## Entorno

- Trabaja dentro del DevContainer o espacio de trabajo Coder.
- Mantén sincronizadas las extensiones entre `.devcontainer/devcontainer.json` y `.vscode/extensions.json`.
- Al añadir tecnologías o dependencias, verifica que `.gitignore` y `.dockerignore` estén actualizados.
