[← SailorBridge](README.md)

# Cuenta y seguridad

Tu **ID de capitán** numérico es tu nombre de inicio de sesión. Sigue asociado a tu cuenta aunque cambies de apodo, contraseña o navegador. Vincula una máquina que controles mientras aún puedas iniciar sesión. La necesitarás si olvidas la contraseña.

## Crear tu cuenta

1. Abre la [aplicación](https://app.sailorbridge.com) y elige **Registrarse**. Introduce el número que quieras, de 3 a 11 dígitos. Si aparece **Ya reclamado**, cambia el número y consulta otro.
2. Comprueba lo que muestra la página para ese número. Los ID normales de 6 a 8 dígitos y todos los de 9 a 11 son gratis. Los ID más cortos y los patrones especiales de hasta 8 dígitos tienen un coste único. Si eliges un número de pago, guarda el **Enlace de canje** al pagar para terminar el registro en otro dispositivo. [Precios](https://www.sailorbridge.com/#pricing)
3. Establece y confirma tu contraseña. Puedes elegir un avatar predefinido o conservar tu inicial. Confirma tu edad, acepta los **Términos del servicio** y elige **Registrarse**. La aplicación inicia tu sesión. [Vincula tu primera máquina](machines.md)

## Iniciar sesión y confirmar un navegador nuevo

Introduce tu **ID de capitán**, elige **Siguiente**, introduce tu **Contraseña** y elige **Iniciar sesión**. Si tienes una máquina vinculada, SailorBridge pide confirmación automáticamente en un navegador nuevo. Con la verificación en dos pasos desactivada, basta con la contraseña en un navegador reconocido. Sin una máquina vinculada ni verificación en dos pasos, también basta con la contraseña en un navegador nuevo. La **Verificación en dos pasos** es opcional. Si la activas, debes confirmar cada inicio de sesión, incluso en un navegador conocido.

En **Confirma que eres tú**, usa uno de los métodos que se ofrecen.

- Para **Código del autenticador**, introduce el código actual de tu aplicación de autenticación.
- Para **Código de la máquina**, ejecuta `sail confirm` en el terminal de una máquina vinculada. Introduce el código de ocho caracteres en la página de inicio de sesión.
- Para la **Confirmación en el navegador**, abre otro navegador conocido donde ya tengas una sesión abierta. En el aviso de confirmación, toca el número de dos dígitos que aparece en la página de inicio de sesión. Aprueba solo un inicio de sesión que hayas iniciado tú. Si lo inició otra persona, elige **No fui yo**.

## Configurar tu perfil y proteger el acceso

Abre **Yo**. Puedes definir un **Apodo** y elegir un **Avatar** de la galería. **Idioma** establece el idioma de la interfaz y el de las respuestas a partir del siguiente turno del chat o tarea. En **Estilo de respuesta**, elige **Principiante** para recibir más explicaciones o **Experto** para respuestas más breves.

Abre **Seguridad** y después **Verificación en dos pasos**. Elige **Activar**, verifica tu contraseña y escanea el código QR con tu aplicación de autenticación. Introduce el código actual y elige **Confirmar y activar**. Para desactivarla, elige **Desactivar la verificación en dos pasos** e introduce tu contraseña y un código nuevo.

Para cambiar la contraseña, rellena **Contraseña actual**, **Nueva contraseña** y **Confirmar nueva contraseña** en **Seguridad**. Introduce un código de autenticación si la verificación en dos pasos está activada. Tras el cambio, la sesión queda abierta en este navegador y se cierra en los demás.

<a name="consultar-la-actividad-y-las-claves-de-los-dispositivos"></a>

## Consultar la actividad y los dispositivos

Abre **Yo**, después **Seguridad** y **Eventos de seguridad recientes**. La lista abarca los últimos 90 días. Si se inicia sesión correctamente desde un navegador nuevo, se te pregunta si fuiste tú. Elige **Fui yo** o **No fui yo**. Cada navegador registra sus propias confirmaciones. Los intentos fallidos aparecen en la lista sin pedirte aprobación.

Si ves un inicio de sesión que no reconoces, cambia tu contraseña. **Cerrar otras sesiones** cierra las sesiones de los demás navegadores y aplicaciones y mantiene abierta esta sesión. Si solo quieres desconectar una máquina, retírala de **Máquinas**. **Revocar todas las máquinas** desconecta todas las máquinas vinculadas. Tendrás que volver a vincular cada una para que pueda trabajar o emitir un código de recuperación. También puedes eliminar un registro de seguridad individual tras confirmarlo. Los demás navegadores siguen recibiendo sus propios avisos hasta que confirmen el evento.

En **Seguridad**, abre **Dispositivos** para ver tus aplicaciones y máquinas vinculadas. Selecciona un dispositivo y elige **Quitar** para impedir que autorice nuevas acciones. Se cerrará la sesión de la aplicación o se desvinculará la máquina. Si el dispositivo ha desaparecido, elige **Perdido o robado**. SailorBridge también dejará de aceptar contenido que ese dispositivo hubiera autorizado.

## Recuperar una contraseña olvidada

1. Ejecuta `sail recover` en el terminal de una máquina vinculada. Muestra tu ID de capitán y un código de recuperación de ocho caracteres, de un solo uso y válido durante 10 minutos. Si pides otro código en la misma máquina, sustituye al primero.
2. En la página de inicio de sesión, elige **¿Olvidaste tu contraseña?**. Introduce el ID y el **Código de recuperación** que aparecen en el terminal. Comprueba el nombre de la máquina y la fecha de vinculación en la página antes de introducir la nueva contraseña.
3. Sigue el procedimiento de recuperación que se muestra. La antigüedad de la máquina se cuenta desde la vinculación o reparación de credenciales más reciente.

| Máquina usada para la recuperación | Verificación en dos pasos | Qué ocurre |
| --- | --- | --- |
| Vinculada hace menos de 72 horas | Cualquier ajuste | Envía una solicitud de recuperación con una espera de 72 horas, aunque tengas un código de autenticación. |
| Vinculada hace al menos 72 horas | Desactivada o activada hace menos de 72 horas | Restablece la contraseña de inmediato con el código de recuperación. La recuperación desactiva la verificación en dos pasos si se activó recientemente. |
| Vinculada hace al menos 72 horas | Activada hace al menos 72 horas | Introduce un código de autenticación para restablecer la contraseña de inmediato y conservar la verificación en dos pasos. Sin él, envía una solicitud de recuperación con una espera de 72 horas. |

Si tienes que esperar, elige **Solicitar recuperación con espera de 72 horas** y respeta el plazo que indica la página de recuperación. Los dispositivos con sesión abierta reciben un aviso. Puedes elegir **Cancelar esta recuperación** en uno de ellos. Un inicio de sesión correcto también cancela la solicitud. Cuando se haga efectivo el cambio, inicia sesión con la contraseña nueva. La recuperación con espera restablece la verificación en dos pasos.

Tras la recuperación, comprueba **Vinculada el** en **Máquinas** y retira las máquinas que no reconozcas. Puedes volver a activar la verificación en dos pasos en **Seguridad**.

## Cerrar sesión o eliminar tu cuenta

Usa **Cerrar sesión** en **Yo** para cerrar la sesión de este navegador. Para cerrar la cuenta, elige **Eliminar cuenta**, comprueba los equipos y las máquinas afectados y confirma con tu contraseña y, si está activada la verificación, con un código de autenticación. La eliminación cierra las sesiones en tus dispositivos, revoca tus máquinas y cancela tu suscripción. Inicia sesión en un plazo de siete días para deshacer la solicitud. Durante ese plazo no puedes recuperar la contraseña porque se han revocado las máquinas. Al vencer el plazo, se elimina la cuenta y su número queda retirado.

## Si algo falla

- Tras cinco intentos fallidos de inicio de sesión en 15 minutos, el bloqueo predeterminado dura 15 minutos. Espera el tiempo indicado. Cada código de autenticación solo se puede usar una vez. Si acabas de usarlo, espera al siguiente.
- Si caducó la confirmación del navegador o tocaste el número incorrecto, vuelve a iniciar sesión. También puedes usar uno de los métodos con código que se ofrecen. Ejecuta `sail confirm` para obtener un nuevo código de inicio de sesión y `sail recover` para obtener otro código de recuperación de contraseña.
- Si una máquina no puede emitir un código de recuperación, prueba con otra máquina vinculada a tu cuenta. Si ninguna tiene credenciales válidas, la cuenta no se puede recuperar. Registra un ID nuevo.
