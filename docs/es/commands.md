[← SailorBridge](README.md)

# Comandos

Usa el chat del equipo para hacer una petición al **Líder** o iniciar un flujo. Usa `sail` en un terminal para gestionar la máquina donde está instalado, consultar el trabajo del equipo o ejecutar un comando en otra máquina del mismo equipo.

## Elegir un comando en el chat del equipo

Abre el **Chat** del equipo y escribe `/`. El menú muestra cuatro atajos, los flujos habilitados del equipo y, al final, `/clear`. Elige una opción, añade la petición en tu idioma y envíala. Los nombres de los comandos se mantienen en inglés. Elegir `/clear` surte efecto de inmediato.

| Qué escribir | Qué ocurre |
| --- | --- |
| `/job #12 What is this waiting for?` | El **Líder** recibe la tarea 12 y tu pregunta. |
| `/event #6 Move this to weekdays.` | El **Líder** recibe el evento programado 6 y el cambio que pides. |
| `/memory #3 When does this apply?` | El **Líder** recibe la entrada de memoria 3 y tu pregunta. |
| `/do Check the current branch.` | El **Líder** hace el trabajo en este turno del chat e informa del resultado, incluido lo que no pudo hacer. |
| `/clear` | Oculta los mensajes anteriores del chat del equipo e inicia una conversación nueva. |

Usa el número de la lista correspondiente del equipo. Las tareas, los eventos y las entradas de memoria tienen sus propios números. **Ir al Chat** en una página de detalles completa el atajo y el número correctos. Para nombrar una máquina, escribe `@` y selecciónala en la lista del equipo.

## Ejecutar un flujo por su nombre

| Comando | Qué obtienes |
| --- | --- |
| `/ask` | Una pregunta cada vez y, después, un resumen de requisitos en el chat. |
| `/plan` | Una tarea de planificación. Lee el plan y decide si quieres poner en cola las tareas propuestas. |
| `/agent` | Un trabajador realiza el trabajo e informa del resultado. |
| `/write-review` | Quien escribe hace el trabajo, ejecuta las comprobaciones y lo corrige según los ajustes de revisión del flujo. |
| `/memory-tidy` | Una tarea que comprueba, combina o elimina entradas de la memoria del equipo. |
| `/docs-tidy` | Una tarea que comprueba los documentos del proyecto e informa de los problemas que requieren tu criterio. |
| `/code-sweep` | Una inspección de solo lectura con tareas de limpieza numeradas que puedes decidir ejecutar. |
| `/write-flow` | Describe una tarea repetible. Cuando se completa correctamente, el flujo nuevo se guarda en el equipo. |
| `/edit-flow` | Indica el nombre del flujo y el cambio. Una edición correcta sustituye un flujo personalizado. Editar un flujo integrado crea uno personalizado con un nombre nuevo. |

Por ejemplo, envía `/agent Count the top-level files in this project.` Si envías tú un flujo en segundo plano, autorizas la tarea. El **Líder** redacta la descripción a partir de la conversación. Si **Iniciar directamente** está activado, tus palabras pasan directamente a la cola. Abre **Ver detalles** en la fila de la tarea en el chat para seguirla. Cuando el **Líder** proponga un flujo en segundo plano en una conversación normal, lee la tarjeta y elige **Sí, Hazlo** para iniciarlo. [Flujos y eventos programados](flows-and-scheduled-events.md)

## Vincular, comprobar o quitar una máquina

| Comando de terminal | Cuándo usarlo |
| --- | --- |
| `sail login` | El comando de instalación lo ejecuta por ti. Ejecútalo de nuevo para obtener otro código de emparejamiento o restablecer el servicio en la misma dirección con las credenciales existentes. |
| `sail host status` | Comprueba la vinculación, la conexión, el servicio, la versión y la ubicación del registro. Añade `--trust` para ver la huella guardada de la clave del servidor. |
| `sail --version` | Muestra la versión instalada. |
| `sail upgrade` | Busca una actualización ahora. El resultado indica si instaló una versión nueva, si ya estaba al día o si la actualización falló. |
| `sail host service status` | Comprueba el servicio en segundo plano. Usa `sail host service install`, `sail host service restart` o `sail host service stop` para instalarlo, reiniciarlo o detenerlo. |
| `sail host run` | Ejecuta el servicio de la máquina en primer plano si no hay otra instancia en marcha. |
| `sail confirm` | Para **Confirma que eres tú**, obtén un código de inicio de sesión de un solo uso en el terminal de una máquina vinculada. |
| `sail recover` | Para **¿Olvidaste tu contraseña?**, obtén tu ID de capitán y un código de recuperación de contraseña de un solo uso en el terminal de una máquina vinculada. |
| `sail uninstall` | Elimina SailorBridge y sus datos locales, incluidas las copias de trabajo y los registros. Conserva tus directorios de proyecto y los inicios de sesión de los motores. |

Para los inicios de sesión de motores, `sail account list` muestra lo que reconoce la máquina. Usa `sail account add <name> <directory>` para registrar un directorio de inicio de sesión, `sail account remove <name>` para quitar un registro o ignorar un inicio de sesión predeterminado y `sail account restore <provider>` para volver a reconocer uno ignorado. Para un endpoint compatible, `sail account create <provider>` escribe una plantilla de configuración en `~/.sailorbridge/`, que `sail uninstall` elimina. [Configurar una cuenta de GLM, DeepSeek o Kimi desde una plantilla](engine-accounts-and-pacing.md#configurar-una-cuenta-de-glm-deepseek-o-kimi-desde-una-plantilla)

## Trabajar con elementos numerados del equipo

En el terminal de una máquina vinculada, ejecuta los comandos siguientes en el directorio de proyecto configurado para el equipo. Usa los números de los elementos de tu equipo. Por ejemplo, la tarea que aparece como `#12` en el chat es `12` en un comando de terminal.

| Tarea | Comandos que puedes ejecutar en el terminal |
| --- | --- |
| Buscar una tarea | `sail job list` enumera las tareas abiertas. Añade `--all` para incluir las finalizadas. `sail job get 12` muestra la tarea 12. Añade `--json` para ver todos los detalles. |
| Detener o eliminar una tarea | `sail job stop 12` detiene la tarea. `sail job delete 12` elimina el registro de una tarea finalizada. |
| Buscar un evento | `sail event list` enumera los eventos habilitados aún pendientes de ejecución. Añade `--all` para incluir los deshabilitados o completados. `sail event get 6` muestra el mensaje y el horario. |
| Eliminar un evento | `sail event delete 6` elimina el evento programado. |
| Eliminar una entrada de memoria | `sail memory delete 3` elimina una entrada de forma permanente. Si está bloqueada, elimínala en **Memoria del equipo** en la aplicación. |

Los comandos siguientes requieren una sesión activa del **Líder** o una tarea. En tu terminal devuelven `local_team_context_missing` incluso en el directorio del equipo. Pide al **Líder** en el chat del equipo lo que necesites. Para trabajar tú mismo con un elemento existente, abre **Lista de tareas**, **Eventos programados** o **Memoria del equipo** en la aplicación. Los trabajadores tienen acceso de solo lectura a las tareas y los eventos.

| Quién lo ejecuta | Tarea y comandos |
| --- | --- |
| **Líder** | `sail job create <flow> "<task>"` pone en cola un flujo en segundo plano. `sail job edit 12 "<revised task>"` cambia una tarea abierta. `sail job retry 12` continúa el trabajo que lo permita con el mismo número. |
| **Líder** | `sail event create "Check the queue" --weekdays 09:00` programa un mensaje del chat del equipo en la zona horaria de la máquina. Otros horarios usan `--once`, `--daily` o `--every`. Usa `--tz` para especificar una zona horaria. `sail event edit 6 --disable` pausa el evento. |
| **Líder** o trabajador | `sail memory list` enumera las entradas. `sail memory titles` enumera los títulos. `sail memory search "release checklist"` devuelve hasta 10 coincidencias. `sail memory get 3` lee la entrada. |
| **Líder** o trabajador | `sail memory create "<title>" "<body>"` guarda un dato o propone una corrección con el mismo título. `sail memory edit 3 "<body>"` cambia una entrada. `sail memory conflicts` enumera los conflictos sin resolver. |
| **Líder** | `sail memory resolve <id> --value "<correct text>"` resuelve un conflicto. Usa el ID del conflicto. Una entrada bloqueada requiere tu decisión en **Memoria del equipo**. |
| **Líder** o trabajador | `sail memory list --tidy` enumera candidatos y versiones. `sail memory review 3 --rev <version>` marca una entrada que merece conservarse. `sail memory merge` admite argumentos `--entry <id>:<version>` repetidos, además de `--title` y `--body`. Entre las tareas de los trabajadores, solo `/memory-tidy` puede eliminar entradas. |

Si un comando indica que hay una decisión pendiente, comprueba el valor actual en la respuesta antes de dar el cambio por aplicado.

## Ejecutar un comando localmente o en otra máquina del equipo

Para un comando local, `sail run git status` envía la salida a tu terminal. Para un comando largo que no sea interactivo, añade `--fold` antes del comando. Recibes el resultado, las últimas líneas de la salida y la ruta al registro completo. Para una ventana local de tmux, `sail tmux read <window>` muestra su texto. `sail tmux send <window> "<text>"` rellena la entrada. Envía `sail tmux send <window> --key Enter` para confirmar la entrada.

Para ejecutar un comando en otra máquina tuya del mismo equipo, empieza en el directorio del equipo y sustituye `build-machine` por el nombre de la máquina de destino. Por ejemplo, `sail exec build-machine git status --short` se ejecuta en el directorio de ese equipo en la máquina de destino. El código de salida y las últimas 40 líneas de la salida combinada, hasta 16 KiB, vuelven al terminal. Usa `--json` antes del nombre de la máquina para obtener un único resultado JSON.

El límite de tiempo predeterminado es de 5 minutos. Para cambiarlo, pon `--timeout` y un número positivo de segundos antes del nombre de la máquina. Una máquina emisora puede esperar el resultado de hasta 8 comandos. Ctrl-C termina la espera en el terminal. El comando remoto puede seguir ejecutándose.

## Si algo falla

- Si no se reconoce un comando de chat, escribe `/` y elige un flujo habilitado. Si una tarjeta de confirmación antigua apunta a un flujo deshabilitado, habilítalo en **Flujos del equipo** o elige un flujo disponible y envía otra petición.
- Si no se encuentra un atajo numerado, abre **Lista de tareas**, **Eventos programados** o **Memoria del equipo** de este equipo. Comprueba el número e incluye `#` en el chat.
- Si `sail exec` no puede identificar el equipo, cambia a uno de los directorios de equipo que aparecen. Si el destino está sin conexión o ha dejado de aceptar trabajo, vuelve a intentarlo cuando esté en línea y acepte trabajo. Un destino en línea tiene hasta 10 minutos para recoger un comando en cola. Si se desconecta antes, el comando espera 60 segundos a que vuelva a conectarse. Si el destino desaparece después de empezar, comprueba qué hizo el comando antes de repetirlo.
