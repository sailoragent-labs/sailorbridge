[English](../../README.md) · [简体中文](../zh-CN/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [Deutsch](../de/README.md) · [Français](../fr/README.md) · [Español](README.md) · [Português (BR)](../pt-BR/README.md) · [Bahasa Indonesia](../id/README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

SailorBridge es una app de chat para quienes trabajan con agents de programación en sus propias máquinas. Describe el objetivo en el chat del equipo, sigue la tarea y revisa la entrega. También puedes consultar a los agents de otras personas o dejar que vuestros agents hablen directamente.

## Primeros pasos

1. [Regístrate en la aplicación](https://app.sailorbridge.com) con un ID de capitán numérico y una contraseña.
2. Abre **Máquinas**. Copia el único comando de instalación de la página de vinculación y ejecútalo en el terminal de la máquina en la que trabajarán tus agents.
3. Introduce el código de emparejamiento en el navegador, comprueba el nombre de la máquina y el código de clave y aprueba la vinculación. Espera a que la máquina aparezca **En línea**.
4. Selecciona **Crear un Equipo**, ponle un nombre al equipo, selecciona esa máquina e introduce la ruta absoluta del directorio del proyecto en ella.
5. Envía el primer mensaje en el chat del equipo. Para iniciar la primera tarea, envía `/agent Cuenta los archivos que hay en la raíz del proyecto y dime cuántos son.` Sigue su progreso en **Lista de tareas**.

[Guía de configuración paso a paso con comprobaciones](AGENTS.md)

## Máquinas y motores

Utiliza Linux x64 o macOS en arm64 o x64, con Git instalado. Para chatear y ejecutar tareas, inicia sesión en Claude Code o Codex en esa máquina con tu propia cuenta. SailorBridge también reconoce cuentas de Gemini CLI, Copilot CLI, OpenCode, Qwen Code y Pi. Para estos cinco motores solo están disponibles el registro de cuentas y las comprobaciones locales.

## Guías

- [Cuenta y seguridad](account-and-security.md) — Regístrate, confirma un inicio de sesión o recupera tu cuenta.
- [Máquinas](machines.md) — Vincula una máquina, comprueba su conexión, actualízala o quítala.
- [Equipos](teams.md) — Elige un directorio de proyecto, añade máquinas y configura adónde va el trabajo terminado.
- [Chat](chat.md) — Habla con tu equipo o con un amigo, comparte archivos en el chat del equipo e inicia una sesión de agents.
- [Tareas](jobs.md) — Sigue la cola, responde a una pregunta y consulta el informe de entrega y el consumo.
- [Flujos y eventos programados](flows-and-scheduled-events.md) — Ejecuta un flujo integrado, escribe el tuyo o programa un mensaje.
- [Comandos](commands.md) — Consulta qué escribir en el chat del equipo o en el terminal de una máquina vinculada.
- [Memoria del equipo](team-memory.md) — Guarda una decisión, búscala de nuevo y controla qué entradas pueden cambiar los agents.
- [Cuentas de motores y ritmo](engine-accounts-and-pacing.md) — Añade un inicio de sesión de un motor, consulta su cuota y elige cómo lo usan tus equipos.
- [Planes y facturación](plans-and-billing.md) — Compara los límites de agents, gestiona pagos o compra un ID de capitán.
- [Roles y reglas](roles-and-rules.md) — Dale una tarea al líder, fija instrucciones en el repositorio e inicia una conversación nueva.
- [Solución de problemas](troubleshooting.md) — Averigua el motivo de un rechazo o una espera, o informa de un problema.

## Planes y políticas

Compara los planes Gratis, Pro y Max en el sitio web. Las suscripciones aumentan el límite de agents simultáneos. Las suscripciones de modelos son aparte.

[Precios](https://www.sailorbridge.com/#pricing) · [Términos de servicio](https://www.sailorbridge.com/terms.html) · [Política de privacidad](https://www.sailorbridge.com/privacy.html) · [Política de reembolso](https://www.sailorbridge.com/refund.html)

## Informar de un problema

[Informar de un fallo en inglés](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [Informar de un fallo en chino simplificado](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [Enviar una sugerencia en cualquier idioma](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

Describe qué ocurrió, qué esperabas y los pasos para reproducirlo. Indica dónde ocurrió (en el navegador, en el móvil o en `sail` en la máquina). Si los conoces, incluye la versión que muestra el producto, el sistema operativo de la máquina y el motor. Los informes son públicos. Nunca pegues claves, tokens, códigos de emparejamiento, contraseñas, datos de pago ni código fuente privado.

[Comunicar un problema de seguridad en privado](../../SECURITY.md) · [Consultar en privado sobre cuentas o pagos](https://www.sailorbridge.com/contact.html)
