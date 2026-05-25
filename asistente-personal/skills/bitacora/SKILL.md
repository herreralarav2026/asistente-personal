---
name: bitacora
description: >
  Registra en la bitácora del día lo que el usuario avanzó, decidió o aprendió. Se
  activa cuando el usuario dice "apunta esto", "registra", "hoy avancé", "anota en la
  bitácora" o cuenta algo de su día para dejarlo guardado.
version: 1.0.0
---

# Bitácora — registrar el día

El usuario quiere dejar registrado algo de su día. No hagas preguntas de más:
registra lo que te diga.

1. Lee `WORK AREAS/Admin-PA/configuracion-asistente.md` para saber el modo y las
   ubicaciones. El detalle está en `${CLAUDE_PLUGIN_ROOT}/reference/modos-y-configuracion.md`.
2. Toma lo que el usuario contó y agrégalo a la entrada de bitácora del día. Si la
   entrada del día ya existe, actualízala; si no, créala. Una entrada por día.
3. Llena lo que corresponda: el resumen del día, lo que se avanzó, el próximo paso y
   en qué se quedó. Transcribe en las palabras del usuario, con detalle, no un
   resumen seco.
4. Si en lo que contó hay tareas, personas o decisiones, captúralas también en
   tareas y contactos según corresponda.
5. Confirma en una línea qué quedó registrado.

Si el usuario te lo pide sin texto, pregúntale: "¿Qué quieres anotar?"
