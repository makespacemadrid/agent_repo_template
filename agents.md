# Guiones para agentes
Pistas rapidas para trabajar con agentes de programacion en esta plantilla.

## Objetivo
Documentar el flujo recomendado para que agentes automaticos (como chatops o asistentes) puedan operar en este repo sin friccion.

## Flujo sugerido
- Usa el contenedor devcontainer para obtener todas las herramientas preinstaladas.
- Abre la carpeta en VS Code y habilita las extensiones recomendadas de IA.
- Ejecuta comandos y scripts desde la terminal del contenedor para que el agente tenga el mismo entorno que el humano.

## Buenas practicas
- Prefiere comandos idempotentes y reproducibles; evita pasos manuales.
- Documenta los comandos clave en el README o en scripts para que el agente pueda reusarlos.
- Mantiene las rutas de trabajo dentro del repo para respetar permisos de escritura.
- Evita borrar o resetear cambios que no hayas creado; confirma antes cualquier accion destructiva.

## Verificacion
- Corre los tests o linters relevantes despues de cambios automaticos.
- Revisa diffs antes de hacer commits generados por agentes.
- Si el agente fallo por permisos o red, ajusta el comando y vuelve a intentarlo en el contenedor.
