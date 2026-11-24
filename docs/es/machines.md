[English](../machines.md) · [简体中文](../zh-CN/machines.md) · [日本語](../ja/machines.md) · [한국어](../ko/machines.md) · [Deutsch](../de/machines.md) · [Français](../fr/machines.md) · [Español](machines.md) · [Português (BR)](../pt-BR/machines.md) · [Bahasa Indonesia](../id/machines.md) · [हिन्दी](../hi/machines.md)

[← SailorBridge](README.md)

# Máquinas

Una máquina es un ordenador que conectas a tu cuenta para ejecutar el líder de un equipo o asumir tareas. Instala `sail` en cada máquina y apruébala en el navegador. Su servicio en segundo plano mantiene la conexión después de cerrar el terminal.

## Instalar y vincular una máquina

1. Usa una máquina que controles con Linux x64 o macOS en arm64 o x64. Instala Git. Para chatear y ejecutar tareas, instala Claude Code o Codex e inicia sesión en esa máquina con tu propia cuenta del motor. Puedes completar la vinculación antes de iniciar sesión en el motor.
2. En la aplicación, abre **Máquinas** y luego **Vincular una nueva máquina**. Copia el comando de instalación que aparece en un terminal de la máquina que quieras conectar. Puedes ejecutarlo desde cualquier directorio. Instala `sail`, inicia la vinculación y muestra un código de ocho caracteres válido durante 10 minutos.
3. Introduce ese código en **Código de emparejamiento** en el navegador y elige **Vincular**. Comprueba el nombre de la máquina, la plataforma y la versión de `sail` que aparecen. En la primera vinculación, lee el aviso antes de aceptarlo. Los agents pueden leer, cambiar y eliminar archivos, usar credenciales y conectarse a la red con los permisos del usuario del sistema operativo que ejecuta `sail`. Usa una máquina o un contenedor dedicado si necesitas aislamiento.
4. Elige **Aprobar máquina**. Mantén la máquina conectada mientras obtiene sus credenciales e inicia el servicio. Cuando **Máquinas** muestre **En línea** y el terminal confirme la conexión, puedes elegir **Configurar Cuentas** o **Crear un Equipo**. [Crear un equipo](teams.md)

## Comprobar la conexión o vincular más máquinas

Abre una máquina en **Máquinas** para ver su nombre, plataforma, **Última conexión**, **Vinculada el** y **Versión del cliente**. Puedes editar el nombre para distinguir mejor las máquinas. En la propia máquina, ejecuta `sail host status` para comprobar la vinculación, la conexión y el estado del servicio, y localizar el registro local.

Para usar otro ordenador, abre **Vincular una nueva máquina** de nuevo y ejecuta el comando mostrado en ese ordenador. Cuando esté en línea, añádelo al equipo y configura allí su carpeta de proyecto. Una máquina puede servir a varios equipos. Cada tarea se ejecuta en una máquina apta de su equipo. [Gestionar las máquinas de un equipo](teams.md)

## Actualizar o reparar una instalación

Las actualizaciones automáticas están activadas de forma predeterminada. Tras verificar una actualización, el servicio se reinicia y retoma el trabajo local. Los pasos terminados se conservan. Un paso local interrumpido puede ejecutarse de nuevo. Para actualizar manualmente, ejecuta `sail upgrade` en la máquina. El resultado indica si se instaló una actualización, si ya estaba al día o si hubo un error. Ejecuta `sail --version` para comprobar la versión instalada.

Si necesitas restablecer el servicio, ejecuta `sail login`. En la misma dirección, reinstala y reinicia el servicio con sus credenciales existentes. Si se rechazan y la máquina sigue registrada, se inicia una vinculación de reparación. El navegador muestra **Volver a vincular una máquina existente** e identifica la máquina que se sustituye. Verifica los datos y aprueba el nuevo código. La máquina conserva sus equipos. Para recuperar la contraseña, la fecha de vinculación pasa a ser la de recepción de las nuevas credenciales.

## Retirar una máquina o desinstalar SailorBridge

Para dejar de usar una máquina en toda tu cuenta, abre el menú de su fila en **Máquinas**, elige **Eliminar** y confirma. Se revocan sus credenciales. Sale de sus equipos y deja de trabajar al recibir el aviso, de inmediato si está conectada o en la siguiente conexión. Se conservan sus copias de trabajo locales. Para volver a usarla, ejecuta `sail login` en ella, aprueba la nueva vinculación y añádela a los equipos que la necesiten.

Para quitar la instalación del ordenador, guarda primero el trabajo que necesites de sus copias de trabajo de SailorBridge. Ejecuta `sail uninstall` en esa máquina. Detiene el servicio y elimina `sail`, la definición del servicio, la entrada que el instalador añadió a la ruta del shell y todo el directorio `~/.sailorbridge/`. Esto incluye las credenciales, los registros de cuentas, los registros de actividad, el historial local de chat, las copias de trabajo y la copia de seguridad de `sail`. Se conservan tus directorios de proyectos y de inicio de sesión de los motores. Para reinstalar, usa el comando de **Vincular una nueva máquina**.

## Si algo falla

- Si la vinculación indica que falta Git, instálalo y ejecuta `sail login` para continuar. Si falta iniciar sesión en el motor, ejecuta `claude login` o `codex login` por separado antes de chatear o iniciar una tarea.
- Si caduca el código, ejecuta `sail login` para obtener otro. Si aparece otra máquina, comprueba el código de emparejamiento en el terminal de la máquina que quieres vincular e introdúcelo de nuevo. Tras aprobar la vinculación, puedes elegir **Cancelar vinculación** hasta que la máquina recoja sus credenciales. Si se aprobó pero la máquina no se conecta en 10 minutos, ejecuta `sail host status` y luego `sail login` para volver a conectarla.
- Si una máquina queda sin conexión de forma inesperada, comprueba la red y el servicio con `sail host status`. El plazo predeterminado para quedar sin conexión es de 90 segundos. El aviso solo aparece tras 10 minutos sin conexión y desaparece al reconectarse.
- Si falla una actualización, abre la máquina para leer el motivo y ejecuta el comando de reparación mostrado como el usuario que instaló `sail`. Si la copia local de seguridad no se puede usar, usa el comando de instalación de la página de vinculación.
- Si la máquina indica que ha cambiado la identidad del servidor, rechaza la conexión. Usa `sail host status --trust` en la máquina para comprobar la huella guardada. Si esperabas ese cambio, ejecuta `sail login`, comprueba la nueva huella en el terminal y aprueba otra vinculación.
- Si `sail login` muestra `origin_mismatch`, sigue el procedimiento de desinstalación anterior antes de cambiar de dirección. Después copia el comando de instalación de la página **Máquinas** de la aplicación que quieres usar. Si las credenciales locales de vinculación no se pueden leer, también tendrás que desinstalar y vincular de nuevo.
- Si `sail uninstall` indica que el servicio no pudo confirmar la retirada, los archivos locales se han eliminado. Abre **Máquinas** y retira allí la entrada.
