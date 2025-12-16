# Notas complementarias para Claude y agentes similares

Lee primero `AGENTS.md` para las reglas generales. Aquí solo se añaden recordatorios específicos para evitar duplicar información.

- Respeta siempre las instrucciones sobre `CURRENT_PLAN.md` y `FOUND_WHILE_WORKING.md`; si ya existen, actualízalos en lugar de reemplazarlos.
- Usa un tono conciso en los archivos compartidos con otros agentes, dejando claro el contexto y los motivos de cada cambio.
- Mantén sincronizadas las recomendaciones de extensiones entre `.devcontainer/devcontainer.json` y `.vscode/extensions.json` cuando edites una de ellas.
- Si tienes dudas, pide aclaraciones al usuario y evita inferir requisitos.
- No copies ni exportes información sensible fuera del repositorio.
- Si hay flujos con Docker o Docker Compose, usa la instancia local para reconstruir imágenes y probar antes de proponer cambios.
- Ejecuta o configura GitHub Actions cuando existan para compilar, probar y distribuir artefactos (incluidas imágenes) en vez de pasos manuales.
