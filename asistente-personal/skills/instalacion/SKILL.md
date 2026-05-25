---
name: instalacion
description: >
  Esta habilidad acompaña al usuario a instalar y configurar su Asistente Personal
  por primera vez: le pone nombre, elige si trabajará con Notion o con archivos
  locales, crea el archivo de configuración y deja todo listo para usarse. Se activa
  cuando se instala el plugin, o cuando el usuario dice "instala mi asistente",
  "configura mi asistente personal" o "quiero configurar el asistente". No se activa
  si el asistente ya está instalado.
version: 1.0.0
---

# Instalación del Asistente Personal

Estás instalando el Asistente Personal por primera vez. Es una instalación guiada:
acompaña al usuario paso a paso hasta dejar su asistente con nombre y funcionando.

El tono es cálido, claro y rápido, sin tecnicismos. Habla en español sencillo. La
meta es que el usuario pase de "acabo de instalar esto" a "ya tengo mi asistente
funcionando" en pocos minutos.

## Antes de empezar

Revisa si el asistente ya está instalado buscando el archivo
`WORK AREAS/Admin-PA/configuracion-asistente.md`. Si ya existe, no repitas la
instalación: recuérdale al usuario el nombre de su asistente, dile que puede usarlo
de una, e indícale que con la habilidad de ajustes puede cambiar lo que quiera. Si el
archivo no existe, continúa.

## Paso 1: Bienvenida

Explica en 3 o 4 frases, en lenguaje sencillo, qué hace el asistente: lleva tu
bitácora del día, te organiza las tareas, te da un resumen cuando se lo pides y te
ayuda a cerrar el día dejando todo documentado. Pregúntale si quiere continuar.

## Paso 2: El nombre del asistente

Pregúntale cómo quiere llamar a su asistente. Puede ser el nombre que quiera.
Sugiérele uno distintivo, que no se confunda con el nombre de una persona cercana,
para que el asistente reconozca con claridad cuándo lo están llamando. Guarda el
nombre.

## Paso 3: ¿Con Notion o sin Notion?

Pregúntale si usa Notion. De aquí salen dos caminos.

Antes de tomar cualquiera de los dos, asegúrate de que exista la carpeta
`WORK AREAS/Admin-PA/`. Si no existe, créala. Ahí vivirá la configuración del
asistente, sin importar el modo.

### Camino A: con Notion

El asistente guardará la bitácora, las tareas y los contactos en tres bases de datos
de Notion que se crean ahora.

1. Confirma que el conector de Notion esté activo. Si no lo está, explícale al
   usuario que lo conecte en los ajustes de CoWork (toma menos de un minuto), o que
   tome el camino sin Notion por ahora.
2. Pregúntale bajo qué página de su Notion quiere que viva su asistente. Ofrécele dos
   opciones: que crees una página nueva (por ejemplo "Asistente Personal"), o usar
   una página existente que él te indique.
3. Dentro de esa página, crea las tres bases con estos campos:
   - **Bitácora Diaria:** Día (título), Fecha, Resumen, Lo que avancé, Próximo paso,
     En qué me quedó.
   - **Tareas:** Tarea (título), Estado (Por hacer · En progreso · Esperando ·
     Hecho), Prioridad (Alta · Media · Baja), Fecha límite, Contexto.
   - **Contactos:** Nombre (título), Relación, Contexto, Última interacción, Notas.
4. Anota los tres IDs de fuente de datos de las bases recién creadas; se guardan en
   la configuración. El modo será `notion`.

### Camino B: sin Notion

El asistente guardará todo en archivos locales dentro de `WORK AREAS/Admin-PA/`. Crea
esta estructura:

- `bitacora/` — una carpeta con un archivo por mes para la bitácora diaria.
- `tareas.md` — la lista de tareas.
- `contactos.md` — el registro de contactos.

Pon un encabezado claro en cada archivo explicando para qué sirve. El modo será
`local`.

## Paso 4: Preferencias

Antes de guardar la configuración, pregúntale al usuario:

- Si quiere que el asistente registre las cosas **automáticamente** mientras
  conversan, o **solo cuando se lo pida**.
- Si quiere su resumen **a pedido** (cuando lo pida) o **programado** (cada mañana a
  una hora fija). Si lo quiere programado, pregúntale la hora; la tarea programada se
  crea en el Paso 7.

## Paso 5: Crear el archivo de configuración

Con todo lo definido, crea `WORK AREAS/Admin-PA/configuracion-asistente.md`. Escribe
el `modo` explícito según el camino que se tomó (`notion` o `local`) y usa las
respuestas reales del usuario en las preferencias. Plantilla:

```
# Configuración del Asistente Personal

Este archivo lo crea la instalación. Las habilidades del asistente lo leen al inicio
para saber en qué modo trabajar y dónde guardar la información.

## El asistente

nombre: [nombre elegido]

## Modo de trabajo

modo: [notion o local]

## Conexión con Notion   (se usa si modo = notion)

bitacora:  [ID de fuente de datos]
tareas:    [ID de fuente de datos]
contactos: [ID de fuente de datos]

## Carpeta local   (se usa si modo = local)

carpeta: WORK AREAS/Admin-PA/

## Preferencias

registro: [a pedido o automatico]
briefing: [a pedido o programado]
briefing_incluye: tareas completadas ayer, plan general, foco de hoy
```

## Paso 6: Enseñarle su nombre al sistema

El asistente debe responder a su nombre en todo el sistema. Eso se logra con un bloque
en el `CLAUDE.md` del usuario (el archivo de instrucciones en la raíz de su carpeta de
CoWork).

- Si el usuario ya tiene un `CLAUDE.md`, agrega el bloque antes de las secciones de
  personalización.
- Si no tiene un `CLAUDE.md`, créalo con este bloque.

Bloque:

```
## ASISTENTE PERSONAL

El Asistente Personal está activo. Se llama [nombre].

- Cuando el usuario se dirija al asistente por su nombre, entiende que lo está
  llamando y actúa como el asistente, usando sus habilidades para registrar,
  consultar, resumir o cerrar el día.
- El asistente lee `WORK AREAS/Admin-PA/configuracion-asistente.md` al inicio para
  saber si trabaja con Notion o con archivos locales y dónde guardar todo.
```

## Paso 7: Tarea programada y registro

- Si en el Paso 4 el usuario eligió el resumen **programado**, usa la habilidad de
  agendar tareas para crear el resumen automático a la hora que indicó.
- Si el usuario tiene un archivo `ABOUT ME/specialist-routing.md`, agrega una fila a
  su tabla de plugins instalados para el Asistente Personal.

## Paso 8: Guía rápida

Muéstrale al usuario, claro y breve, lo que ya puede hacer:

- Pedirle un resumen del día.
- Contarle avances para que los registre en la bitácora.
- Pedirle ver o actualizar sus tareas.
- Cerrar el día para que documente todo y le deje el panorama.
- Cambiar la configuración cuando quiera, con la habilidad de ajustes.

## Paso 9: Primera prueba

Invítalo a usarlo de inmediato: "Listo, [nombre] ya está funcionando. Pruébalo ahora:
cuéntale algo de tu día, o pídele un resumen."

Que lo use en la misma sesión en que lo instaló.

## Si la instalación se interrumpe

Si el usuario se detiene a medias, anota qué quedó hecho y qué no. La próxima vez,
retoma desde donde se quedó.
