---
name: cierre
description: >
  Cierra el día: reconstruye lo que pasó, propone un resumen para que el usuario lo
  valide y luego lo documenta donde corresponde. Se activa cuando el usuario dice
  "cerremos el día", "cierre", "terminé por hoy" o quiere cerrar su sesión de trabajo.
version: 1.0.0
---

# Cierre del día

El usuario quiere cerrar su día de trabajo.

Regla principal: **no le preguntes qué hizo.** Nada de "¿qué avanzaron hoy?" ni
"¿cuáles son los siguientes pasos?". Tu trabajo es reconstruir el día tú mismo,
proponerle qué vas a documentar, y documentarlo solo cuando él lo valide.

Lee `WORK AREAS/Admin-PA/configuracion-asistente.md` para saber el modo y las
ubicaciones. El detalle está en `${CLAUDE_PLUGIN_ROOT}/reference/modos-y-configuracion.md`.

## Parte 1: Reconstruir el día

Reúne lo que pasó sin preguntarle nada al usuario:

- Revisa la conversación actual y, si tienes acceso a ellas, las demás conversaciones
  del día. Identifica en qué se avanzó, qué se terminó, qué decisiones o acuerdos
  hubo, y qué pendientes nuevos salieron.
- Entra a Notion y revisa el estado actual: las tareas, los hitos y frentes, y la
  entrada de bitácora del día.

## Parte 2: Proponer y validar

Arma un resumen claro de todo lo que vas a documentar y preséntaselo al usuario
**antes de escribir nada en Notion**. Con títulos y bullets cortos:

- `### Lo que voy a registrar en la bitácora` — los avances y acuerdos del día.
- `### Cambios en tareas e hitos` — qué marco como hecho, qué agrego, qué actualizo.
- `### Para la próxima sesión` — en qué conviene avanzar.

Cierra con una sola pregunta: "¿Lo documento así, o ajustamos algo?". Esa es la única
pregunta que le haces en todo el cierre.

## Parte 3: Documentar

Cuando el usuario valide, o después de aplicar los ajustes que pida, documenta todo
en su sitio según el modo: la entrada de bitácora del día, las tareas y los hitos. No
dupliques la entrada de bitácora del día: si ya existe, actualízala.

Confirma en una línea que quedó documentado y cierra con una frase breve usando tu
nombre.
