# Modos y configuración

Este archivo explica cómo las habilidades del Asistente Personal saben dónde leer y
escribir. Toda habilidad debe consultarlo antes de guardar o consultar información.

## Primer paso de cualquier habilidad

Lee el archivo `WORK AREAS/Admin-PA/configuracion-asistente.md`. De ahí salen tres
cosas: el `nombre` del asistente, el `modo` de trabajo y las ubicaciones.

Si el archivo no existe, el asistente todavía no está instalado: dirige al usuario a
la habilidad de instalación y no continúes.

## Los dos modos

### Modo Notion

El asistente trabaja contra tres bases de datos de Notion. Sus IDs de fuente de
datos están en la configuración:

- `bitacora` — la Bitácora Diaria. Una entrada por día.
- `tareas` — la base de Tareas.
- `contactos` — la base de Contactos.

Para crear, leer o actualizar entradas, usa las herramientas de Notion con esos IDs.

### Modo local

El asistente trabaja contra archivos dentro de la carpeta indicada en la
configuración (por defecto `WORK AREAS/Admin-PA/`):

- `bitacora/` — un archivo por mes, una entrada por día.
- `tareas.md` — la lista de tareas.
- `contactos.md` — el registro de contactos.

## Cómo se guarda cada cosa

Los campos son los mismos en los dos modos; solo cambia el lugar.

- **Entrada de bitácora:** el día, la fecha, un resumen, lo que se avanzó, el
  próximo paso y en qué se quedó. Un día es una entrada: si la del día ya existe, se
  actualiza, no se duplica.
- **Tarea:** la tarea, su estado, su prioridad, fecha límite si tiene, y un contexto
  corto de dónde salió.
- **Contacto:** nombre, relación, contexto, última interacción y notas.

## Cómo registrar

Al capturar, transcribe en las palabras del usuario, no hagas un resumen seco. El
objetivo es que el usuario pueda volver semanas después y acordarse de todo. Ante la
duda, captura de más.

## Cómo detectar tareas en lo que cuenta el usuario

Cuando el usuario habla, hay frases que delatan un pendiente. Detéctalas sin que él
tenga que decir "crea una tarea":

- **Obligación:** "tengo que", "necesito", "debo", "voy a".
- **Recordatorios:** "recuérdame", "que no se me olvide", "dar seguimiento".
- **Compromisos con otros:** "le dije que", "quedé en", "le voy a enviar".
- **En espera:** "estoy esperando que", "me van a mandar" (la tarea queda en estado
  Esperando).

No es tarea algo que ya se hizo, algo hipotético ("tal vez debería") ni una
observación suelta. Ante la duda, captúrala: es más barato que sobre una tarea a que
se te olvide un compromiso.

Cuando el usuario mencione una fecha ("para el viernes", "la próxima semana"),
conviértela a una fecha concreta.

## El nombre del asistente

El campo `nombre` de la configuración es como se llama el asistente. Úsalo al
presentarte y al cerrar. Cuando el usuario se dirija al asistente por ese nombre,
entiende que te está llamando a ti.

## Regla de oro

El usuario nunca debería tener que pensar en archivos, IDs ni modos. Él habla; tú
resuelves dónde va cada cosa según esta configuración.
