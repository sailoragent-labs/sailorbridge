[English](../troubleshooting.md) · [简体中文](../zh-CN/troubleshooting.md) · [日本語](../ja/troubleshooting.md) · [한국어](../ko/troubleshooting.md) · [Deutsch](../de/troubleshooting.md) · [Français](../fr/troubleshooting.md) · [Español](troubleshooting.md) · [Português (BR)](../pt-BR/troubleshooting.md) · [Bahasa Indonesia](../id/troubleshooting.md) · [हिन्दी](../hi/troubleshooting.md)

[← SailorBridge](README.md)

# Solución de problemas

Empieza donde se detuvo el trabajo. Si se trata de un inicio de sesión o un pago, lee el mensaje de esa página. Si hay un problema con una máquina, consulta su terminal. Para una tarea, abre **Lista de tareas**, selecciónala y lee **Por qué no está en curso**. Indica si la tarea requiere que hagas algo o si se reanudará sola.

## Recuperar el acceso a tu cuenta

| Qué ves | Qué hacer |
| --- | --- |
| Tu ID de capitán está ocupado o ya no se admiten más registros hoy | Prueba otro ID disponible. Si se alcanzó el límite diario de registros gratuitos, vuelve mañana. Para un ID de pago, usa el **Enlace de canje** original para completar el registro. |
| **Confirma que eres tú** tras introducir tu contraseña | Usa tu aplicación de autenticación, ejecuta `sail confirm` en una máquina vinculada e introduce su código o, si se ofrece, confirma el número mostrado en un navegador reconocido. Usa la solicitud de inicio de sesión más reciente. Si caduca, vuelve a iniciar sesión. |
| Demasiados intentos fallidos o código de autenticación reutilizado | Tras 5 fallos en 15 minutos, el bloqueo predeterminado dura 15 minutos. Espera el tiempo indicado. Si ya usaste un código de autenticación, espera al siguiente. |
| Olvidaste tu contraseña o caducó el código de recuperación | Ejecuta `sail recover` en el terminal de una máquina vinculada. Elige **¿Olvidaste tu contraseña?** e introduce el ID de capitán y el código de 8 caracteres que muestra. El código dura 10 minutos y funciona una sola vez. Un código nuevo de la misma máquina sustituye al anterior. Si se rechazan las credenciales de la máquina, prueba otra máquina vinculada. Sin una máquina vinculada utilizable, debes registrar un ID nuevo. |
| **Recuperación de cuenta pendiente** | Una máquina vinculada hace menos de 72 horas requiere una espera de 72 horas, también tras una reparación que haya sustituido sus credenciales. Si lleva más tiempo vinculada y la verificación en dos pasos lleva al menos 72 horas activada, necesitas el código de autenticación para recuperar el acceso de inmediato. Sin él, envía la solicitud con una espera de 72 horas. Espera hasta la hora indicada. Si no solicitaste la recuperación, elige **Cancelar esta recuperación** en un dispositivo con sesión abierta. |

## Hacer funcionar una máquina o un equipo

- Si la instalación se detiene porque falta Git, instálalo y vuelve a ejecutar el comando de **Vincular una nueva máquina**. Si Claude Code o Codex no tiene una sesión abierta, puedes completar la vinculación. Ejecuta `claude login` o `codex login` en la máquina antes de pedirle trabajo al equipo.
- Si caduca el código de emparejamiento, ejecuta `sail login` para obtener otro. Introdúcelo en **Vincular una nueva máquina**, elige **Vincular** y comprueba el nombre y los detalles de la máquina que aparece. En la primera vinculación, lee y acepta el aviso, elige **Aprobar máquina** y espera a que se conecte.
- Si la máquina no se conecta en 10 minutos, ejecuta `sail host status`. Muestra el estado del servicio y la ruta del registro. En la misma dirección, ejecuta `sail login` para restablecer el servicio. Si aparece `origin_mismatch` y quieres cambiar de dirección, `sail uninstall` elimina los datos locales de SailorBridge, incluidas las copias de trabajo de las tareas. Ejecuta después el comando de instalación de la página **Máquinas** de la aplicación deseada y vincula la máquina de nuevo.
- Si falla una actualización, abre la máquina en **Máquinas**, consulta el motivo y sigue el comando de reparación indicado. Si falló la descarga, vuelve a intentarlo más tarde con `sail upgrade`. Si falló la escritura, comprueba el espacio en disco y usa la cuenta que instaló `sail`.
- Si la creación del equipo pide una máquina, vincula una y espera a que aparezca **En línea**. Si no puedes quitar la última máquina del equipo, usa primero **Añadir una máquina**. Si no se puede crear el directorio del equipo, elige **Cambiar el directorio en los ajustes del equipo**. Usa una ruta de directorio absoluta en la máquina donde se produjo el error. Un archivo en ese lugar, la falta de permiso de escritura o un disco de solo lectura pueden impedir la creación. [Máquinas](machines.md) · [Equipos](teams.md)

## Obtener una respuesta en el chat

- Si la máquina del **Líder** está sin conexión, el chat del equipo guarda tu mensaje y lo entrega cuando vuelve a conectarse. Si el equipo no tiene ninguna máquina utilizable, añade una y envía otra vez el mensaje.
- Si el motor necesita iniciar sesión, hazlo en la máquina indicada. Si todas las cuentas que puede usar el **Líder** agotaron la cuota, vuelve a enviar el mensaje tras el restablecimiento. Si se rechaza un modelo, sigue las instrucciones de actualización del motor y vuelve a intentarlo o selecciona una cuenta y un modelo disponibles. [Cuentas de motores y ritmo](engine-accounts-and-pacing.md)
- Si tu mensaje respondió a una pregunta en vez de llegar al **Líder**, responde la pregunta abierta o elige **Detener** en su tarjeta. Envía después el mensaje. Si se sustituyó una tarjeta de confirmación o ya se respondió, revisa la última tarjeta o la tarea antes de actuar.
- Si se rechaza un archivo, usa el chat del equipo y envía como máximo 4 adjuntos por mensaje, de hasta 5 MiB cada uno. Se admiten PNG, JPEG, WebP, PDF, texto sin formato y Markdown. Vuelve a seleccionar cualquier adjunto no disponible. Una carga no enviada caduca tras 24 horas. Si alcanzaste el límite de 1 GiB de la cuenta, espera a que caduquen los archivos enviados, a los 30 días, para liberar espacio. Si un mensaje pesa demasiado, divídelo en mensajes de como máximo 64 KiB.
- En una sesión de agents, si la cuenta necesita iniciar sesión o recuperar cuota, soluciona primero ese problema y después elige **Reanudar**. Si una sesión entre equipos alcanza el límite de rondas, el destinatario puede ampliarla en 10 o 20 rondas o elegir **Rondas ilimitadas**. La persona que inició la sesión espera al destinatario. [Chat](chat.md)

## Averiguar por qué espera una tarea

Abre la tarea en **Lista de tareas**. Lee **Por qué no está en curso** antes de decidir si reinicias algo.

| Qué retiene la tarea | Qué hacer |
| --- | --- |
| El reparto está en pausa o esta tarea está pausada | Usa **Reanudar el reparto** para el equipo o **Reanudar** para la tarea individual. |
| Las máquinas están ocupadas, el equipo alcanzó su límite de tareas o tu plan alcanzó su límite de agents | El trabajo empieza cuando se libera una plaza. Consulta **Trabajos simultáneos** para el equipo o **Límite de concurrencia** en **Suscripción** para tu cuenta. |
| La tarea necesita que alguien escriba y alguien revise | Elige **Ir a cuentas**. Asegúrate de que una máquina del equipo tiene las cuentas necesarias habilitadas para ambos pasos. Quien escribe en una máquina y quien revisa en otra no pueden ejecutar juntos la misma tarea. |
| La máquina alcanzó el umbral de ritmo o agotó la cuota | Espera el tiempo estimado que aparece. Si la espera se debe al ritmo, **Cambiar a Sin Límite** cambia el ritmo de todos tus equipos tras confirmarlo. Si se agotó la cuota, la tarea vuelve a comprobarla y se reanuda en la misma máquina cuando la recupera. |
| La tarea necesita una respuesta o un requisito previo | Elige **Responder** si la pregunta es para ti. Tras 5 minutos de espera, la tarea libera su plaza. Cuando respondas, continúa cuando su máquina original quede libre. Para un requisito previo, abre la tarea del número que se muestra y comprueba su resultado. |
| Una máquina rechazó la tarea o dejó de comunicarse | Lee el motivo que figura debajo de la tarea. Otra máquina apta puede tomar una tarea rechazada. Si todas las candidatas la rechazaron, abre **Nota de la máquina** para ver sus motivos. Si la máquina que la ejecutaba perdió la conexión, puede reanudar si vuelve antes. Tras 30 minutos sin renovar la toma, otra máquina puede comenzar desde el principio. |
| **Incompleto** o **Fallida** | Abre **Informe de entrega** para ver el último paso, el motivo y el trabajo conservado. Corrige el problema indicado. Usa **Continuar** si se ofrece para retomar la misma tarea a partir del trabajo conservado o **Rehacer** para empezar de nuevo. Si falló una subida, el informe indica la rama, el commit y el comando de subida del trabajo guardado localmente. |

## Corregir un comando, horario o entrada de memoria

- Si el terminal dice «Ejecuta este comando dentro de un trabajo o de una sesión del líder del equipo.» (`local_team_context_missing`), el comando requiere una sesión activa incluso en el directorio del equipo. Pregunta al **Líder** en el chat del equipo o abre **Lista de tareas**, **Eventos programados** o **Memoria del equipo** para trabajar con un elemento existente. [Comandos para elementos numerados del equipo](commands.md#trabajar-con-elementos-numerados-del-equipo)
- Si no se reconoce un comando con barra, escribe `/` para ver los flujos habilitados. Si falta una referencia numerada, comprueba el equipo y el tipo de elemento correctos y escribe `#` antes de su número en el chat. Si `sail exec` indica que el destino está sin conexión, el comando no se inició. Si el resultado se perdió *después* de iniciarse, comprueba el destino antes de repetirlo. [Comandos](commands.md)
- Si se rechaza un evento programado, elige una hora futura para un evento de una sola vez o un intervalo de 5 a 720 minutos para uno recurrente. Un equipo puede tener hasta 20 eventos. Elimina uno que no necesites para liberar espacio. Debes volver a crear un evento de una sola vez que ya terminó para repetirlo. Si un evento hace referencia a un flujo deshabilitado o a un número que falta, corrige el mensaje para la próxima ejecución. [Flujos y eventos programados](flows-and-scheduled-events.md)
- Si se rechaza un cambio de memoria, abre **Memoria del equipo**. Puedes cambiar allí las entradas bloqueadas. Si alguien la cambió antes, lee el contenido más reciente antes de guardar. Si agotaste el espacio para entradas fijadas, deja de fijar una o acórtala antes de fijar otra. [Memoria del equipo](team-memory.md)

## Comprobar un pago que no se ha completado

Si el pago está pendiente, vuelve a la compra original y consulta su estado antes de volver a pagar. Si aparece **Pago fallido** en una suscripción, **Actualizar Método de Pago y Pagar Deuda** abre el pago del saldo pendiente. [Planes y facturación](plans-and-billing.md)

## Si algo falla

Si el problema sigue, anota los pasos, el mensaje exacto, qué esperabas y dónde ocurrió. Incluye la versión, el sistema operativo de la máquina y el motor si los conoces. Para un problema de cuenta o pago, usa el contacto privado que figura en el README. Si es de seguridad, usa su enlace privado. No incluyas credenciales, códigos de emparejamiento, datos de pago ni código fuente privado en los informes públicos. [Informar de un problema](README.md#informar-de-un-problema)
