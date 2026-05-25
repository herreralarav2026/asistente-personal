---
name: resumen
description: >
  Da el resumen del día a pedido: lo que se completó, el panorama general y el foco
  para hoy. Se activa cuando el usuario pide su resumen, su briefing o su repaso del
  día.
version: 1.0.0
---

# Resumen — el repaso del día

El usuario pide su resumen. Dáselo claro y escaneable.

1. Lee `WORK AREAS/Admin-PA/configuracion-asistente.md` para saber el modo, las
   ubicaciones y la preferencia `briefing_incluye`. El detalle de los modos está en
   `${CLAUDE_PLUGIN_ROOT}/reference/modos-y-configuracion.md`.
2. Reúne lo que indique `briefing_incluye`. Por defecto incluye:
   - **Lo completado el día anterior:** las tareas que pasaron a hecho y los avances
     de la última entrada de bitácora.
   - **El panorama general:** cómo van los hitos o los pendientes mayores.
   - **El foco de hoy:** las tareas para hoy o las siguientes a atender.
   Toma los datos de Notion o de los archivos locales, según el modo.
3. Preséntalo en el chat con títulos y bullets cortos, sin relleno:
   - `### Lo que cerraste`
   - `### El panorama`
   - `### En qué enfocarte hoy`
4. Si el asistente está recién instalado y no hay datos, dilo con honestidad en lugar
   de inventar.
