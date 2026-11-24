[← SailorBridge](README.md)

# Cuentas de motores y ritmo

Tus agents usan cuentas de motores con sesión iniciada en tus máquinas. Puedes ver qué cuentas puede usar un equipo, cuánta cuota queda y cuándo se reanudará el trabajo. Un plan de SailorBridge establece cuántos agents pueden ejecutarse a la vez. El acceso a los modelos y la cuota dependen del proveedor del motor.

## Buscar o añadir una cuenta

1. Inicia sesión en Claude Code o Codex en la máquina donde quieras ejecutar el motor. Ejecuta `sail account list`. El inicio de sesión predeterminado se detecta automáticamente. Su nombre suele ser el del motor seguido de `@` y del nombre de la máquina.
2. Para añadir otro inicio de sesión, inicia sesión en el motor en un directorio de cuenta independiente. Ejecuta `sail account add <name> <directory>` con ese directorio y un nombre de 1 a 64 caracteres, único en la máquina, sin espacios ni barras. Por ejemplo, si tu segundo inicio de sesión está en esa ubicación, ejecuta `sail account add work "$HOME/codex-work"`. La siguiente consulta de cuota lo detecta sin reiniciar.
3. Abre **Recursos** y luego **Cuentas**. Selecciona la cuenta para ver sus máquinas, cuota y modelos disponibles. Las cuentas que el mismo motor comunica con el mismo nombre desde distintas máquinas aparecen en una sola fila. El directorio de inicio de sesión, el correo electrónico y las credenciales permanecen en la máquina.

Codex usa un inicio de sesión con suscripción. Claude Code admite un inicio de sesión con suscripción o una clave de API. Para Gemini CLI, Copilot CLI, OpenCode, Qwen Code y Pi solo están disponibles el registro de cuentas y las comprobaciones locales. De esos cinco, Gemini CLI y OpenCode reconocen directorios independientes con nombre propio.

## Usar un endpoint compatible con Claude

Para un proveedor como DeepSeek o GLM, configura un directorio de cuenta de Claude Code independiente en tu máquina. En su archivo `settings.json`, establece la URL base del proveedor en `env.ANTHROPIC_BASE_URL` y su credencial en `env.ANTHROPIC_API_KEY` o `env.ANTHROPIC_AUTH_TOKEN`. Asigna a `ANTHROPIC_MODEL`, en el mismo objeto `env`, el nombre del modelo del proveedor. Puedes asignar por separado las familias Opus, Sonnet y Haiku usando `ANTHROPIC_DEFAULT_OPUS_MODEL`, `ANTHROPIC_DEFAULT_SONNET_MODEL` y `ANTHROPIC_DEFAULT_HAIKU_MODEL`.

Ejecuta allí `sail account add <name> <directory>` con el nombre y la ruta que elegiste. La cuenta funciona a través de Claude Code. Abre **Modelos disponibles** para ver los nombres de modelos leídos del directorio. Los modelos del endpoint usan esas asignaciones y no tienen ajuste de esfuerzo. Los detalles de la tarea muestran el modelo que realmente se ejecutó.

## Configurar una cuenta de GLM, DeepSeek o Kimi desde una plantilla

`sail account create` escribe un archivo local de configuración de Claude Code con el endpoint del proveedor, los modelos propuestos para los niveles alto, medio y bajo y un marcador para la clave, sin pedir, leer ni enviar tu clave ni registrar la cuenta.

Para configurar GLM, ejecuta lo siguiente en la máquina donde quieras usar la cuenta.

```sh
sail account create glm
```

El comando muestra tres líneas. Aquí, `~` representa tu directorio personal.

```text
Modelos propuestos (Opus/Fable, Sonnet, Haiku/subagente): glm-5.3, glm-5.2, glm-5.3-flash.
Hay tres modelos distintos. Sonnet es el nivel medio propuesto.
Edita ~/.sailorbridge/account-templates/glm/settings.json, sustituye el marcador por tu clave de API y ejecuta sail account add <name> ~/.sailorbridge/account-templates/glm.
```

El archivo `settings.json` generado contiene esta plantilla.

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "REPLACE_WITH_YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "ANTHROPIC_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-5.3-flash",
    "ANTHROPIC_DEFAULT_FABLE_MODEL": "glm-5.3",
    "CLAUDE_CODE_SUBAGENT_MODEL": "glm-5.3-flash"
  }
}
```

Abre el archivo en un editor de texto como `nano`.

```sh
nano ~/.sailorbridge/account-templates/glm/settings.json
```

Sustituye `REPLACE_WITH_YOUR_API_KEY` por tu propia clave de GLM, conserva las comillas y guarda el archivo. Registra el directorio con el nombre que elijas. En este ejemplo se usa `glm`. El nombre debe ser único en esa máquina, tener de 1 a 64 caracteres y no contener espacios en blanco ni `/`.

```sh
sail account add glm ~/.sailorbridge/account-templates/glm
sail account list
```

Busca `glm` en la lista del terminal. Cuando la máquina comunique la cuenta, abre **Recursos** y después **Cuentas** en la aplicación. Selecciona `glm` para ver sus **Modelos disponibles**.

Para DeepSeek o Kimi, empieza con el comando de tu proveedor. Abre el archivo `settings.json` en la ruta que muestra el comando y sustituye el marcador por la clave de tu proveedor. Usa el comando `sail account add` que aparece con el nombre elegido y comprueba después `sail account list`.

| Comando de plantilla | Endpoint en el archivo | Modelos propuestos que se muestran |
| --- | --- | --- |
| `sail account create deepseek` | `https://api.deepseek.com/anthropic` | El nivel alto usa `deepseek-v4-pro`. Los niveles medio y bajo comparten `deepseek-flash`. |
| `sail account create kimi` | `https://api.kimi.com/coding/` | Usa una clave del Kimi Coding Plan. Los tres niveles usan `k3.1-pro[1m]`. |

MiniMax requiere `--region international` o `--region china`. GLM, DeepSeek y Kimi rechazan `--region`.

## Consultar la cuota y reservar una parte para ti

Abre la cuenta en **Cuentas**. Consulta **Cuota**, **Reinicio** y **Lectura** juntos. Una lectura de una suscripción puede mostrar una ventana de cinco horas, una ventana semanal o una asignación semanal para un modelo concreto. Codex informa de su cuota semanal estándar. Consultar la cuota no consume tokens del modelo. Si falla una nueva lectura, puede aparecer una lectura correcta de hasta una hora de antigüedad, marcada como antigua. Si falta la lectura, se indica el motivo y la cuenta puede seguir siendo apta para trabajar.

- **Habilitada** controla las nuevas asignaciones a esta cuenta en todos tus equipos. Si se desactiva, el trabajo que ya está en curso puede terminar.
- **Umbral de reserva** reserva un porcentaje para tu propio uso. Fíjalo entre 0 % y 100 % en pasos de 5. Si en una ventana de más de un día queda ese porcentaje o menos, los trabajadores y el **Líder** dejan de usar la cuenta. Las ventanas cortas usan toda su asignación.
- Para una cuenta medida por gasto, fija **Límite mensual** en el máximo que quieras que esa máquina use durante un mes natural. Esto se aplica, por ejemplo, a DeepSeek. GLM proporciona su propia lectura de cuota. Cuando se alcanza el límite, el trabajo nuevo espera hasta la medianoche UTC del primer día del mes siguiente, salvo que aumentes el límite. Un paso en curso puede terminar por encima del límite. Si registras la misma cuenta en varias máquinas, cada una mide su propio gasto. Si aparece **Coste no disponible**, ves el recuento de tokens y el límite no se puede aplicar.
- **Créditos de reinicio** aparecen cuando Claude o Codex informa de ellos. Abre un crédito, comprueba qué restablece y cuándo caduca, elige **Canjear** y confirma. **Canjear reinicio** en la lista de cuentas usa el crédito apto que caduca primero. La máquina que tiene la cuenta realiza el restablecimiento. Comprueba el resultado antes de usar otro crédito.

## Elegir cuentas y modelos para un equipo

Abre **Lista de cuentas** en el menú del chat del equipo. Las cuentas de las máquinas del equipo se incluyen de forma predeterminada. Configura **Función** en **Ambos**, **Solo escribir** o **Solo revisar** para controlar qué pasos pueden usar una cuenta. Usa **Solo líder** para reservarla para el chat de ese equipo. **Quitar del equipo** y **Añadir cuenta al equipo** cambian su disponibilidad para ese equipo.

En **Detalles del equipo**, abre los ajustes de reparto. En **Modelo del Líder**, elige una cuenta habilitada de una máquina del equipo, después uno de sus modelos detectados y, si se ofrece, un nivel de esfuerzo. Elegir la cuenta de otra máquina mueve allí al **Líder** para el mensaje siguiente. Si la cuenta elegida no puede ejecutarse, la respuesta identifica el motor y el modelo alternativos.

Para los trabajadores, indica el modelo y el esfuerzo preferidos para cada nivel de dificultad y motor en los ajustes de modelos del equipo. Las opciones de escritura y revisión de un flujo eligen el motor. En la revisión automática, se evita, si es posible, la familia de modelos que se usó realmente para escribir. Si un flujo pide un motor para el que el equipo no tiene cuenta en ese rol, la tarea puede usar selección automática en esa ejecución. Los detalles de la tarea explican el cambio.

Una tarea necesita una máquina que pueda realizar todos sus pasos. En esa máquina, cada paso usa una cuenta habilitada y admitida para su motor y rol. Entre las cuentas aptas, tiene prioridad un inicio de sesión pendiente de renovación. Le siguen las cuentas cuya cuota se restablece dentro de un día, primero la que antes se restablezca. Si el restablecimiento es más tarde, se tienen en cuenta la cuota utilizable, la capacidad del plan y el tiempo que queda. Las cuentas sin lectura van al final. Una revisión de los cambios desde la revisión anterior, o una primera revisión de hasta 120 líneas modificadas, da preferencia a un plan más pequeño con capacidad libre.

## Ajustar el ritmo del trabajo nuevo

Abre **Recursos** y luego **Modo de Ritmo**. La opción predeterminada, **Según Cuota**, reparte el trabajo a lo largo de la ventana de cuota. Una cuenta va por delante del ritmo si su porcentaje consumido supera al porcentaje de tiempo transcurrido en más de 100/7 puntos porcentuales (unos 14,3) y queda más de un séptimo de la ventana. Si todas las cuentas aptas van por delante, la máquina espera antes de tomar una tarea nueva. Una tarea en curso puede continuar. El chat con el **Líder** también puede continuar.

Elige **Sin Límite** para que todos tus equipos tomen tareas nuevas sin esperar por ese límite de ritmo. Las reservas de las cuentas y las ventanas agotadas se siguen aplicando. Si una cuenta está seleccionada para el **Líder** de alguno de tus equipos y queda menos del 10 % en una ventana aplicable a toda la cuenta, los trabajadores la dejan para el chat. Puedes volver a **Según Cuota** en la misma página.

## Si algo falla

- Si el archivo de plantilla ya existe, el comando se niega a sobrescribirlo y muestra su ruta. Edita ese archivo y registra su directorio.
- Si el comando rechaza un directorio, comprueba la ruta que muestra. El directorio debe pertenecer a tu usuario y tener el modo `0700` para que solo tú puedas acceder a él. Cuando el propietario y los permisos sean correctos, ejecuta de nuevo el comando de plantilla.
- `sail uninstall` elimina `~/.sailorbridge/`, incluidos estos archivos de configuración, así que guarda también una copia de tu clave en otro lugar.
- Si falla el registro, sigue el comando de inicio de sesión que muestra el terminal para el directorio que indicaste. El directorio debe identificar un único motor. Usa `sail account list` para comprobar el nombre. Para quitar un registro o ignorar un inicio de sesión predeterminado, ejecuta `sail account remove <name>`. Las credenciales locales se conservan. Para volver a reconocer un inicio de sesión predeterminado, ejecuta `sail account restore claude` o `sail account restore codex`, o abre **Inicios de sesión ignorados** en la máquina y elige **Restaurar**.
- Si aparece **Sesión caducada**, vuelve a iniciar sesión en la máquina indicada. Si aparece **Renovar sesión**, la máquina intenta renovar la sesión. Si aparece **Red no disponible**, comprueba la conexión de esa máquina. Si el proveedor limita las solicitudes o no está disponible, se reintenta tras una pausa. Si la cuenta muestra **Modelos Aún No Leídos** en el selector de modelos, espera una lectura o elige una cuenta con un modelo detectado.
- Si un equipo impide quitar la cuenta de su **Líder**, elige primero otra en **Modelo del Líder**. Si falta quien escriba o revise una tarea, elige **Ir a cuentas** en sus detalles y habilita el rol que falta en una máquina capaz de ejecutar toda la tarea.
- Abre **Lista de tareas** y lee **Por qué no está en curso**. Una espera por ritmo indica un tiempo estimado. Puedes esperar o confirmar **Cambiar a Sin Límite** para todos tus equipos. Una tarea que ha agotado la cuota de sus cuentas utilizables espera en la misma máquina y vuelve a comprobarla a la hora indicada. Iniciar sesión o recuperar cuota hace que se reanude automáticamente.
