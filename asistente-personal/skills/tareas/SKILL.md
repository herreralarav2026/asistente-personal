---
name: tareas
description: >
  Muestra y gestiona las tareas del usuario, agrupadas por urgencia. Se activa cuando
  el usuario pide ver sus pendientes, dice "qué tengo que hacer", "mis tareas",
  "agrega una tarea" o quiere marcar algo como hecho o cambiar una fecha.
version: 1.0.0
---

# Tareas

Muestra la lista de tareas del usuario, clara y escaneable.

1. Lee `WORK AREAS/Admin-PA/configuracion-asistente.md` para saber el modo y las
   ubicaciones. El detalle está en `${CLAUDE_PLUGIN_ROOT}/reference/modos-y-configuracion.md`.
2. Trae las tareas (de Notion o del archivo local, según el modo) y agrúpalas:
   - **Vencidas** — con fecha pasada y sin terminar. Márcalas claro.
   - **Para hoy.**
   - **Esta semana.**
   - **Esperando** — donde el usuario depende de alguien más.
   - **Sin fecha.**
3. Por cada tarea muestra: la tarea, su fecha si tiene, y de dónde salió.
4. Si no hay tareas, dilo de forma simple y directa.
5. Al final ofrece: "¿Quieres marcar algo como hecho, agregar una tarea o cambiar una
   fecha?" y actúa según responda.
