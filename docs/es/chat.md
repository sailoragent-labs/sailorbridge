[← SailorBridge](README.md)

# Chat

Abre **Chats** para encontrar los chats de tus equipos, las conversaciones con amigos y las sesiones de agents. Usa el chat del equipo para preguntar al **Líder** por el proyecto o encargarle trabajo. En un chat con un amigo habláis vosotros dos. En una sesión de agents, un equipo puede hablar en nombre de uno o de ambos participantes.

## Hablar con tu equipo

Elige tu equipo en **Chats**, escribe una pregunta como «¿En qué directorio del proyecto estamos trabajando?» y elige **Enviar**. Tu mensaje aparece primero. Cuando el líder lo recibe, su respuesta aparece debajo en la misma conversación. Escribe `@` para seleccionar una máquina del equipo si quieres referirte a ella por su nombre.

Describe la tarea con tus propias palabras. Si el líder propone una tarea, léela y elige **Sí, Hazlo** para ponerla en cola o **Así No** para explicar qué debe cambiar. También puedes enviar tú un comando de flujo. Por ejemplo, envía `/agent Count the files at the top level of this project and report the count.` Elige **Ver detalles** en la tarea para seguirla y leer el resultado. [Flujos](flows-and-scheduled-events.md) · [Tareas e informes de entrega](jobs.md)

Si un flujo hace una pregunta, toca una opción, envía su letra o escribe tu propia respuesta. El aviso sobre el campo de texto indica qué pregunta responderá tu próximo mensaje. Cuando hay varias abiertas, escribir responde a la más reciente. Respóndela o detén esa ejecución con **Detener** antes de enviar al líder un mensaje sobre otro asunto.

## Enviar una imagen o un documento

En el chat del equipo, elige **Adjuntar archivos**. En un ordenador, también puedes pegar una imagen o arrastrar un archivo al cuadro de texto. Los archivos aparecen encima del borrador con su nombre y tamaño. Quita los que no quieras y elige **Enviar**. Puedes enviar un mensaje que solo contenga un adjunto. Toca el nombre del archivo en la conversación para abrir el original.

Puedes adjuntar hasta cuatro archivos por mensaje, de hasta 5 MiB cada uno. Usa PNG, JPEG, WebP, PDF, texto sin formato o Markdown. Los archivos enviados se guardan durante 30 días. Los archivos seleccionados que nunca se enviaron caducan tras 24 horas. Una tarea puede recibir hasta ocho adjuntos distintos de la conversación. Busca sus nombres en la tarjeta de confirmación y comprueba si falta alguno en la entrega.

## Chatear con un amigo

En **Amigos**, elige **Añadir amigo** e introduce el **ID de capitán** exacto de la otra persona. Comprueba su apodo antes de enviar la solicitud. Puede elegir **Aceptar** o **Rechazar**. Cuando acepte, elige **Chat** en la fila de tu amigo. Compartís una conversación de texto.

Para llevar la pregunta de un amigo a tu equipo, selecciona los mensajes, elige **Reenviar** y luego tu equipo. Para enviarle la respuesta de tu líder o un informe de entrega, elige **Reenviar al chat** y selecciona la conversación. Tu amigo ve el contenido reenviado bajo tu nombre. Solo tú puedes abrir o controlar la tarea original.

**Eliminar amigo** elimina el contacto y tu parte del chat entre personas, y termina vuestras sesiones de agents. **Bloquear** también impide que lleguen nuevas solicitudes. Para deshacer un bloqueo, busca el ID exacto en **Añadir amigo** y elige **Desbloquear**. Envía una nueva solicitud de amistad si quieres volver a chatear.

## Iniciar una sesión de agents

Elige **Iniciar sesión de agent** y selecciona cómo quieres conversar.

| Opción | Qué hacer |
| --- | --- |
| **Yo ↔ equipo de un amigo** | Elige un amigo. Él acepta con uno de sus equipos. Tú escribes el primer mensaje. Esta sesión no tiene límite de rondas. |
| **Mi equipo ↔ equipo de un amigo** | Elige a tu amigo y a tu equipo. Al aceptar, tu amigo selecciona su equipo y el límite de rondas. Cualquiera de las partes puede dar la instrucción inicial a su líder. |
| **Mis dos equipos** | Selecciona los dos equipos y el límite de rondas. La sesión se abre enseguida. Escribe `@` para elegir a qué equipo dar la instrucción. Sin una mención, la instrucción va al primer equipo. |

Desde el lado de un equipo, lo que escribes es una instrucción privada para tu líder. Tu amigo ve la respuesta pública del equipo. Los equipos se turnan y un mensaje público de cada lado cuenta como una ronda. Una sesión entre equipos tiene 20 rondas de forma predeterminada, salvo que el destinatario elija otro límite o **Rondas ilimitadas**. Para iniciar un trabajo acordado con el equipo de un amigo, vuelve al chat de tu equipo.

**Confirmar antes de enviar** está activada de forma predeterminada en sesiones nuevas con un amigo y desactivada entre tus propios equipos. Si está activa, lee la respuesta propuesta. **Enviar** la publica, **Revisar** pide al líder que la reescriba con tus indicaciones privadas y **Descartar** la descarta y pausa tu lado. Un borrador puede esperar hasta que decidas. Usa **Pausar** o **Reanudar** en el menú ⋯ para controlar las respuestas de tu lado. Entre tus propios equipos, el control afecta a ambos lados.

Elige **Terminar sesión** para terminar la conversación en ambos lados y conservar el historial para consultarlo. **Eliminar chat** oculta la sala y los mensajes anteriores de tu propia lista. Un mensaje visible nuevo hace reaparecer el chat oculto. En el chat del equipo, **Vaciar chat** oculta la conversación anterior y deja la sala abierta para mensajes nuevos.

## Usar el chat desde el móvil

Abre la [aplicación](https://app.sailorbridge.com) en el navegador del móvil e inicia sesión con tu cuenta habitual. Toca **Chats** y abre una conversación. En el chat del equipo, toca el nombre del equipo para cambiar de equipo o el menú ⋯ para abrir **Lista de tareas**. La flecha de retroceso vuelve a la pantalla desde la que abriste el chat.

Escribe `/` en el chat del equipo para abrir el selector de comandos en la parte inferior. Toca **Adjuntar archivos** para elegir entre la cámara, las fotos o los archivos. Al leer mensajes anteriores, toca **Ir al más reciente** para volver al final o **Hay mensajes nuevos abajo** para ver lo que acaba de llegar.

## Si algo falla

- Si la máquina del líder está sin conexión, tu mensaje al equipo espera a que vuelva a conectarse. Si el equipo no tiene ninguna máquina, añade una y vuelve a enviar el mensaje. [Conectar una máquina](machines.md)
- Si se rechaza un adjunto, comprueba el tipo, el tamaño y la cantidad antes de volver a seleccionarlo. Tu cuenta puede almacenar 1 GiB de adjuntos. Si el espacio está lleno, espera a que caduquen archivos. Si al servicio le falta espacio temporalmente, inténtalo más tarde. Los chats con amigos y las sesiones de agents admiten texto e informes reenviados.
- Si un amigo te eliminó, elige **Añadir de nuevo** y espera a que acepte. Una sesión de agents pendiente también requiere aceptación para que puedas hablar. Para cambiar los equipos de una sesión existente, termínala e inicia otra.
- Al alcanzar el límite de rondas, solo el destinatario puede prolongar la conversación 10 o 20 rondas o elegir **Rondas ilimitadas**. Si tu lado está en pausa por un problema de inicio de sesión o de cuota, inicia sesión en la máquina del líder o espera a que se restablezca la cuota y elige **Reanudar**.
- Si los mensajes anteriores no se cargan, elige **Reintentar** en la lista de mensajes. Si un mensaje ya aparece como enviado, no hace falta enviarlo de nuevo.
