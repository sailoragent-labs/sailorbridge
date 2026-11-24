[← SailorBridge](README.md)

# Flujos y eventos programados

Un flujo permite a tu equipo repetir una tarea. Tiene un nombre que puedes escribir en el chat y pasos y opciones guardados para ese equipo. Un evento programado envía un mensaje al chat del equipo a la hora que elijas. El mensaje puede hacer una pregunta al líder o iniciar un flujo.

## Buscar y ejecutar un flujo

En el chat del equipo, escribe `/` para ver los flujos habilitados y sus descripciones. Elige un flujo, añade lo que quieres que haga y envía el mensaje. Por ejemplo, `/ask What should the export include?` inicia una conversación sobre ese requisito. Un flujo interactivo pregunta en el chat. Un flujo en segundo plano entra en **Lista de tareas**.

Cuando envías un comando de flujo en segundo plano, el **Líder** suele usar la conversación para redactar la descripción y poner la tarea en cola. Si **Iniciar directamente** está activado para ese flujo, tu texto pasa a ser la descripción y la tarea entra en cola de inmediato. La opción está desactivada de forma predeterminada en los flujos integrados en segundo plano. Cuando el líder propone una tarea por su cuenta, elige **Sí, Hazlo** para iniciarla.

| Flujo integrado | Cuándo usarlo y qué obtienes |
| --- | --- |
| `/ask` | Aclara una decisión. Responde a una pregunta cada vez para recibir un resumen de requisitos. |
| `/plan` | Planifica un trabajo que requiere varias tareas. Lee el plan y el lote propuesto, y elige **Poner Todas en Cola**, **Revisar Plan** o **Ahora No**. El plan es en sí una tarea que puedes seguir. |
| `/agent` | Encarga a un trabajador un trabajo mecánico o que lleve tiempo. Un trabajador lo realiza e informa del resultado sin una ronda de revisión. |
| `/write-review` | Encarga una implementación al equipo e indica cómo comprobarla. Quien escribe hace el trabajo. Se ejecutan las comprobaciones y tanto quien escribe como quien revisa examinan el resultado. |
| `/memory-tidy` | Revisa la memoria del equipo, quita las entradas que hayan perdido valor y combina duplicados. La entrega enumera las acciones y las sugerencias que requieren tu decisión. El equipo también puede hacerlo automáticamente si hay entradas que atender, como máximo una vez en 24 horas. |
| `/docs-tidy` | Vuelve a comprobar la documentación afectada por los cambios y comprueba el resto por muestreo rotativo. La entrega distingue las correcciones mecánicas de las preguntas para ti. |
| `/code-sweep` | Inspecciona el código para detectar posibles limpiezas. Lee las propuestas numeradas de la entrega e indica al líder cuáles debe realizar. La inspección es de solo lectura. |
| `/write-flow` y `/edit-flow` | Describe una tarea repetible para crear un flujo o indica cómo debe cambiar uno existente. El resultado se guarda para tu equipo. |

## Elegir quién escribe y quién revisa

Abre ⋯ en el chat del equipo, elige **Flujos del equipo** y abre `/write-review`. La página muestra los pasos y las opciones de las futuras tareas de este equipo.

| Opción | Cómo usarla |
| --- | --- |
| **Quién escribe** | Mantén **Automático** para seleccionar un proveedor según la dificultad o selecciona un motor para los pasos de escritura. |
| **Quién revisa** | Mantén **Automático** para buscar un revisor independiente de otra familia de modelos o selecciona un motor para la revisión. Quien escribe hace su propia autorrevisión. Los ajustes de modelos del equipo determinan los modelos que se usan. |
| **Pasadas de autorrevisión** | Elige entre 0 y 10, con 3 como valor predeterminado. En cada ronda, quien escribe comprueba su trabajo, corrige los problemas detectados y vuelve a comprobar hasta que una pasada no encuentra nada o se alcanza el límite. Usa 0 para omitir la autorrevisión. |
| **Cuántas rondas como máximo** | Elige entre 0 y 10, con 6 como valor predeterminado. Usa 0 para el modo Solo, que omite la revisión independiente y conserva tu ajuste de autorrevisión. |

Un hallazgo P1 requiere otra revisión del cambio completo. Los hallazgos menos graves requieren revisar las correcciones. Desde la tercera ronda, si no hay P1, quien escribe puede acabar las correcciones pendientes y entregar sin otra revisión. Si quedan P1 al alcanzar el límite de rondas, abre **Informe de entrega** para ver los hallazgos que detuvieron la tarea.

Para fusionar código, la comprobación aplicable completa debe superarse en el commit final. Si no hay una comprobación aplicable para un cambio exclusivamente de documentación, un revisor independiente debe aceptar el motivo. En modo Solo, un cambio sin una comprobación que ejecutar queda **Incompleto**. [Consultar las comprobaciones y la entrega de una tarea](jobs.md)

## Escribir o editar un flujo del equipo

1. En el chat del equipo, envía `/write-flow` seguido de los pasos, los criterios de finalización, qué hacer si falla un paso y qué entregar. Por ejemplo, `/write-flow List Markdown files changed since the last commit. Report their paths. If none changed, say so.`
2. Si quien escribe necesita una decisión, responde a la pregunta en el chat. Una vez escrito y comprobado el flujo, el chat muestra el nombre con el que se ha guardado. Elige **Ver flujo** para leer su descripción, sus pasos y sus opciones. Su nombre ya está disponible en el menú `/`.
3. Para modificar el flujo, elige **Editar en el chat** o envía `/edit-flow <name> <change>`. Indica qué debe cambiar y qué debe conservarse. Editar un flujo personalizado sustituye la versión del equipo. Editar uno integrado crea uno personalizado con otro nombre. Consulta la entrega para ver los valores efectivos de las opciones y las reglas de pasos que se quitaron al editarlo.

También puedes editar las opciones de un flujo en su página de detalles. Si sigue instrucciones guardadas, puedes editarlas allí para la próxima ejecución. Desactiva **Activado** para retirar el flujo del menú del equipo para nuevas ejecuciones. Las tareas en cola y en curso pueden terminar. Los dos comandos de escritura de flujos siguen disponibles.

## Programar un mensaje

1. En el menú ⋯ del equipo, abre **Eventos programados** y usa el botón más para **Añadir evento**. En **Qué quieres decir**, escribe el mensaje que quieres enviar, de hasta 16 KiB. Por ejemplo, `/docs-tidy Check the project documentation.`
2. Selecciona **Frecuencia**. Elige **Una vez** para una fecha y hora locales futuras, **Cada día** para una hora cada día o **Días laborables** de lunes a viernes. Con **Cada pocos minutos**, fija **Intervalo (minutos)** entre 5 y 720. Usa **Desde** y **Hasta** para limitarlo a una parte del día.
3. Comprueba **Zona horaria**, que al principio es la de tu navegador, y guarda. La lista muestra la primera línea del mensaje y la próxima hora de ejecución. Crear el evento autoriza el mensaje. A la hora fijada, aparece en el chat bajo tu nombre con la marca **Programado**. Cada activación usa un turno completo del líder.

Las horas siguen la zona horaria seleccionada. Si un cambio de hora omite una hora programada, el evento usa la siguiente hora válida. Si el reloj repite esa hora, usa la primera aparición. Un evento por intervalos con una franja horaria omite las ejecuciones fuera de ella.

Abre el evento para cambiar su mensaje o su horario. Al guardar se vuelve a calcular la próxima ejecución. Desactiva el evento para detener los futuros mensajes y actívalo cuando quieras reanudarlo. Al reactivarse, empieza desde ese momento. Tras una interrupción del servicio de programación, solo se envía la ejecución omitida más reciente. Busca un evento por su texto o número exacto, como `#6`. Usa **Completado** para encontrar un evento de una sola vez que ya terminó.

## Si algo falla

- Si el chat no reconoce un flujo, escribe `/` para ver los nombres habilitados para el equipo. Vuelve a habilitar el flujo en **Flujos del equipo** si hace falta. Si un plan no puede poner el lote en cola porque `/write-review` está deshabilitado, actívalo antes de volver a enviar el trabajo.
- Un equipo puede tener 30 flujos personalizados. Al llegar al límite, elimina uno que ya no necesites antes de crear otro. Si un nombre ya está en uso, edita ese flujo o elige otro nombre. Si la edición indica que una regla de paso eliminada es demasiado larga para incluirla en la entrega, acórtala o muévela en la página del flujo y vuelve a intentar el cambio.
- Un equipo puede tener hasta 20 eventos programados. Al llegar al límite, elimina un evento antes de añadir otro. Si un evento de una sola vez ya se ejecutó, crea otro para repetirlo. Usa una hora futura y un intervalo dentro del rango indicado.
- Si un mensaje programado menciona un flujo ausente o deshabilitado o un elemento numerado que falta, esa ejecución se consume. Corrige el mensaje o habilita el flujo antes de la próxima ejecución. Si un flujo interactivo programado indica que otro está ocupado, espera a una activación posterior.
