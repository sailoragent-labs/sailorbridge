[← SailorBridge](README.md)

# Tareas

Una tarea es una ejecución de un flujo. Cada equipo tiene una cola que comparten sus máquinas. Puedes encargar una tarea al equipo en el chat, seguir su progreso por número y abrir su entrega para ver qué produjo y qué requiere aún tu atención.

## Poner trabajo en cola

En el chat del equipo, envía el nombre de un flujo y un encargo, por ejemplo `/agent Count the files at the top level of this project and report the count.` La tarea entra en cola y una máquina apta la recoge cuando tiene capacidad. Esa máquina ejecuta la tarea en su propia copia de trabajo.

Si el **Líder** propone un trabajo en la conversación, lee la propuesta y elige **Sí, Hazlo** para ponerlo en cola. En un plan con varias tareas, lee la lista antes de elegir **Poner Todas en Cola**. **Revisar Plan** te permite describir un cambio. **Ahora No** deja el lote fuera de la cola. Tras la aceptación, cada tarea recibe su propio número. [Elegir un flujo](flows-and-scheduled-events.md)

## Buscar una tarea y consultar su estado

Abre el menú ⋯ en el chat del equipo y elige **Lista de tareas**, o elige **Ver detalles** en la tarea del chat. La lista muestra primero **Activa** y después recuerda tu último filtro en ese navegador. Elige **Todas** para incluir las tareas finalizadas. Busca por el texto de la tarea o el nombre del flujo, o escribe el número completo con su almohadilla, como `#6`, para encontrarlo con cualquier filtro.

| Qué ves | Qué significa |
| --- | --- |
| **Cola** | La tarea está a la espera de que la recoja una máquina. La línea inferior indica el motivo. Si se menciona un número de tarea, identifica un requisito previo. |
| **Activa** | Una máquina ha recogido la tarea. Ábrela para ver la etapa actual y la máquina. |
| **Esperando al líder** o **Esperándote** | El líder se ocupa de las preguntas que puede responder. Si necesita que decidas, elige **Responder** y responde en el chat. El filtro **Tú** muestra las tareas que esperan tu respuesta. |
| **Hecha** | El flujo entregó su resultado. **Terminado, comprobaciones fallidas** indica que hay una entrega con una comprobación fallida. Lee la comprobación antes de usar el resultado. |
| **Incompleto** | El flujo terminó antes de entregar todo lo pedido. Consulta dónde se detuvo y qué falta. Se conserva el trabajo ya producido. |
| **Fallida** | Un error terminó la ejecución. Abre el informe y **Nota de la máquina** para ver el motivo. |
| **Cancelada** | La tarea se detuvo. Su registro permanece en la lista. |

**En pausa** y **Cuota** también pueden explicar por qué una tarea está inactiva. Abre **Por qué no está en curso** para ver qué espera y qué acción puedes realizar, si hay alguna.

## Consultar la tarea, la entrega y el consumo

Selecciona la fila numerada. **Detalles de la tarea** muestra el estado, **En ejecución** y **Rondas**. **Información de la tarea** incluye la máquina, quién inició la tarea y **En cola**. Despliega **Pasos** para ver qué etapa se ejecutó, cuánto tardó y qué motor y modelo usó. Si aparece, **Problemas de calidad** muestra los hallazgos de la autorrevisión, la revisión independiente y su última ronda.

Cuando termine la tarea, abre **Informe de entrega**. Lee **Cambios**, **Comprobaciones**, **Observaciones de revisión**, **Sin cotejar** y **Necesita tu decisión**. Si una tarea completada tiene una comprobación fallida, esta aparece primero. Si la tarea generó commits, consulta dónde quedaron. Si la máquina no pudo subirlos, el informe indica la rama local, el commit, el motivo y un comando que puedes ejecutar. Una tarea que solo pide un informe puede entregar su respuesta sin un commit.

Abre **Uso** y despliega **Por ronda** para ver el recuento de tokens y los modelos utilizados. El uso se registra por proveedor, cuenta y modelo. Los totales de la entrega corresponden a la última vez que una máquina recogió la tarea. El tiempo en cola se registra por separado del tiempo de ejecución.

## Pausar, cambiar, detener o continuar una tarea

- En una tarea en cola, elige **Pausar** para impedir que las máquinas la recojan y después **Reanudar** cuando pueda ejecutarse de nuevo. Elige **Empezar ahora** para moverla al principio de la cola. Si una plaza está ocupada, puedes seguir esperando o detener expresamente una tarea en curso para liberarla.
- Para revisar una tarea abierta, elige **Ir al Chat** desde la tarea. Se completa su número. Añade tus requisitos nuevos y envía el mensaje. Si el líder propone un cambio, elige **Sí, Cambiar**. En una tarea en cola, la nueva descripción sustituye a la anterior. Si estaba en ejecución, el intento se detiene y vuelve a la cola con el mismo número.
- Para terminar una tarea, elige **Detener** y confirma. Si la detienes expresamente, necesita tu instrucción para continuar. Si una tarea finalizada tiene un punto de reanudación guardado y trabajo utilizable, abre ⋯ y elige **Continuar**. Usa el mismo número y la copia de trabajo conservada o la rama subida. Si cambias los requisitos antes de continuar, empieza desde el principio.
- Elige **Rehacer** para poner en cola una tarea nueva con el flujo, la descripción, el repositorio y las opciones originales. Recibe un número nuevo y puedes seguir leyendo la anterior. Úsalo cuando **Continuar** no esté disponible. **Eliminar** quita permanentemente el registro de una tarea finalizada tras confirmarlo.

## Si algo falla

- Si el reparto está en pausa para todo el equipo, elige **Reanudar el reparto** para que las máquinas tomen tareas nuevas. Si el equipo o tu cuenta alcanzó el límite de concurrencia, la tarea empieza cuando se libera una plaza. [Ajustes de reparto del equipo](teams.md)
- Si una tarea espera tu respuesta, puedes contestar incluso después de los primeros cinco minutos. A los cinco minutos, la máquina libera la plaza. Tras tu respuesta, la misma máquina reanuda en cuanto queda libre.
- Si una tarea necesita quien escriba o revise, elige **Ir a cuentas**. Una sola máquina debe tener las cuentas necesarias para toda la tarea. Si todas las máquinas candidatas la rechazaron, la tarea falla y sus notas indican los motivos. Si la espera se debe a la cuota o al ritmo, consulta el tiempo estimado. El trabajo se reanuda cuando hay cuota o capacidad disponible. [Cuentas de motores y ritmo](engine-accounts-and-pacing.md)
- Si una máquina pierde el contacto, puede reanudar cuando se reconecte. Tras 30 minutos sin renovar la toma de la tarea, otra máquina del equipo puede recogerla y empezar desde el principio. Tres pérdidas de contacto de la misma tarea la terminan con **Fallida**. Comprueba la máquina antes de continuar o repetir. [Comprobar la máquina](machines.md)
- Un fallo recuperable del sistema permite continuar automáticamente hasta 10 veces durante la vida de una tarea. Si sigue finalizada, lee su último informe, corrige la causa y usa **Continuar** si se ofrece.
