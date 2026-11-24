[English](../../AGENTS.md) · [简体中文](../zh-CN/AGENTS.md) · [日本語](../ja/AGENTS.md) · [한국어](../ko/AGENTS.md) · [Deutsch](../de/AGENTS.md) · [Français](../fr/AGENTS.md) · [Español](AGENTS.md) · [Português (BR)](../pt-BR/AGENTS.md) · [Bahasa Indonesia](../id/AGENTS.md) · [हिन्दी](../hi/AGENTS.md)

# Guía de configuración de SailorBridge

## 1. Preparar la máquina

Utiliza una máquina que controles con Linux x64 o macOS en arm64 o x64. Instala Git y uno de estos motores, Claude Code o Codex. Inicia sesión en el motor con tu propia cuenta y elige el directorio del proyecto en el que trabajará el equipo.

**Comprobación** — Tanto `git --version` como `claude --version` o `codex --version`, según el motor, muestran una versión. Si el motor está instalado pero no has iniciado sesión, ejecuta `claude login` o `codex login` en esa máquina. Puedes vincularla antes de iniciar sesión en el motor. Inicia sesión antes de chatear o ejecutar una tarea.

## 2. Registrarse en el navegador

Abre la [aplicación](https://app.sailorbridge.com) y elige **Registrarse**. Para seguir esta guía, introduce un ID de capitán numérico que aparezca como disponible y gratuito, establece una contraseña, confirma tu edad y acepta los términos de servicio.

**Comprobación** — Se abre la aplicación y puedes entrar en **Máquinas**.

## 3. Ejecutar el comando de instalación

En **Máquinas**, abre **Vincular una nueva máquina**. Copia el único comando de instalación que aparece y ejecútalo en la máquina del paso 1. El comando instala `sail` e inicia la vinculación automáticamente.

**Comprobación** — El terminal muestra un código de emparejamiento de ocho caracteres y el tiempo restante. Si caduca, ejecuta `sail login` para obtener otro.

- **¿Ya está vinculada a esta dirección?** Ejecuta `sail host status`. Si está conectada, pasa al paso 5. Para restablecer el servicio en la misma dirección, ejecuta `sail login`. El servicio se reinicia con las credenciales existentes.
- **¿Dirección incorrecta (`origin_mismatch`)?** Para cambiarla, ejecuta `sail uninstall`. Después, copia el comando de instalación de la página Máquinas de la aplicación a la que quieres conectarte y ejecútalo. La desinstalación elimina los datos locales de SailorBridge, incluidas sus copias de trabajo.

## 4. Aprobar la máquina

Introduce el código de emparejamiento en la página de vinculación del navegador y selecciona **Vincular**. Comprueba el nombre y los detalles de la máquina que aparece. En la primera vinculación, lee y acepta el aviso sobre los permisos del usuario que ejecuta `sail` y elige **Aprobar máquina**.

**Comprobación** — Espera a que la máquina aparezca **En línea** en **Máquinas**. El terminal también confirma que está vinculada y en línea.

## 5. Crear un equipo

Elige **Crear un Equipo**. Ponle un nombre al equipo, selecciona la máquina en línea y escribe en **Directorio del proyecto** la ruta absoluta en esa máquina. Si el directorio no existe, SailorBridge lo crea la primera vez que se usa. En **Destino**, mantén la opción predeterminada **Autofusión** para fusionar los cambios en la rama principal remota, o elige **Rama** para subir cada tarea a su propia rama para revisión. Crea el equipo.

**Comprobación** — El nuevo equipo muestra la máquina seleccionada con el estado **En línea**.

## 6. Enviar el primer mensaje

Abre el **Chat** del equipo y pregunta «¿En qué directorio del proyecto estamos trabajando?».

**Comprobación** — El **Líder** responde en el mismo chat.

## 7. Completar la primera tarea

Envía `/agent Cuenta los archivos que hay en la raíz del proyecto y dime cuántos son.` en el chat del equipo. Abre **⋯ → Lista de tareas** para seguir la tarea.

**Comprobación** — La tarea muestra el estado **Hecha**. Abre el **Informe de entrega** para ver el número de archivos.
