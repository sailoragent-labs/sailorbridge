[← SailorBridge](README.md)

# Roles y reglas

Cada equipo tiene un **Líder**. Hablas con él en el chat del equipo. Responde preguntas, ejecuta comandos breves y encarga el trabajo más largo a un flujo. Un trabajador ejecuta un paso de ese flujo en una máquina del equipo. Las instrucciones permanentes para el motor se guardan en el repositorio del proyecto. No hay un editor de roles ni una biblioteca de reglas.

## Encargar el trabajo al equipo

Abre el **Chat** de tu equipo. Pregunta «¿En qué rama estamos?». El **Líder** puede comprobar el directorio del equipo y responder en el chat. Para una comprobación rápida en otra máquina del equipo, escribe `@`, selecciona la máquina e indica qué debe comprobar. Recibirás un resumen del resultado.

Para un trabajo que quieras recibir y revisar, envía una petición como «Actualiza las instrucciones de configuración y pide que las revisen». Cuando el **Líder** proponga un flujo en segundo plano, lee la tarea en la tarjeta. Elige **Sí, Hazlo** para ponerla en cola o **Así No** para explicar qué debe cambiar. Abre **Lista de tareas** para seguir los pasos de los trabajadores. Si un trabajador necesita una decisión, el **Líder** comprueba qué sabe ya el equipo y te pregunta en el chat si necesita tu respuesta.

## Dar una instrucción permanente al motor

Guarda las instrucciones de todo el proyecto en el archivo `AGENTS.md` del repositorio para Codex o en `CLAUDE.md` para Claude Code. Por ejemplo, anota qué comando ejecutar antes de entregar un cambio. El motor lee su archivo de instrucciones al trabajar en ese repositorio. Si quieres que el equipo recuerde un dato entre tareas, también puedes pedírselo en el chat. [Memoria del equipo](team-memory.md)

## Retomar una conversación tras una pausa

Envía el siguiente mensaje en el mismo chat del equipo. El **Líder** puede iniciar una nueva sesión del motor tras una pausa larga, un cambio de motor o el traslado a otra máquina. Recupera el resumen guardado del equipo, los mensajes recientes, la memoria del equipo y las tareas pendientes. Si aparece **Organizando la conversación…**, puedes enviar el mensaje igualmente. El **Líder** responde cuando termina de resumir.

## Si algo falla

- Si falta un detalle anterior, indica el número de tarea, la decisión o el archivo pertinente en tu siguiente mensaje. Una sesión nueva recibe los 20 mensajes más recientes y un resumen si está disponible.
- Si persiste una instrucción errónea de una conversación anterior, elige **Vaciar chat**, comprueba el nombre del equipo y confirma. Los mensajes anteriores desaparecen de la vista del chat y la siguiente sesión empieza sin el resumen anterior. Si la instrucción procede de un archivo del repositorio o de la memoria del equipo, corrígela allí.
- Si el **Líder** agota el tiempo, divide la petición en pasos más pequeños o envía el trabajo más largo como tarea. [Comandos](commands.md)
