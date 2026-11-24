[← SailorBridge](README.md)

# Equipos

Un equipo da a un proyecto su propio chat con el **Líder**, una cola de tareas, memoria del equipo y una o varias máquinas. Puedes tener varios equipos y usar la misma máquina en más de uno. Solo tú puedes ver y cambiar los ajustes de tu equipo.

## Crear un equipo para tu proyecto

1. Vincula la máquina en la que se ejecutará el líder. Cuando aparezca **En línea**, elige **Crear un Equipo** en la página de vinculación. También puedes ir a **Equipos** y elegir **Crear equipo**. [Vincular una máquina](machines.md)
2. Introduce un **Nombre del equipo** y selecciona esa máquina. Puedes elegir un **Avatar**, además de una cuenta, un modelo y un nivel de esfuerzo para el líder entre las opciones de esa máquina, o dejar los valores predeterminados.
3. En **Directorio del proyecto**, introduce la ruta absoluta de la máquina seleccionada, empezando por `/`. Si ya trabajas en un repositorio, usa su directorio local. Si quieres trabajar en un repositorio remoto existente, clónalo primero en esa máquina y configura allí sus credenciales de Git. SailorBridge detecta la rama principal del repositorio.
4. Elige un **Destino** y selecciona **Crear equipo**. El equipo muestra ahora la máquina. Abre el **Chat** para hablar con el líder. [Usar el chat del equipo](chat.md)

La primera vez que el equipo usa la ruta, abre la carpeta existente o la crea. Si es una carpeta normal con archivos, inicializa Git y crea una instantánea inicial. Si la carpeta contiene varios repositorios de Git directamente debajo, indica al líder cuál quieres usar. Cada tarea trabaja en un único repositorio. El trabajo que abarca varios se divide en tareas independientes.

## Elegir adónde van los cambios

Abre tu equipo en **Equipos** para llegar a **Detalles del equipo**. Cambia allí **Directorio del proyecto** o **Destino**. Los cambios se aplican a partir de la siguiente tarea que tome una máquina.

| Destino | Dónde están los commits de una tarea |
| --- | --- |
| **Autofusión** (predeterminado) | La máquina intenta subir los cambios a la rama principal remota y después adelanta por fast-forward su rama principal local. Revisa la entrega si avanzó la rama principal o el remoto exige revisión. Si se indica una rama de tarea, fusiónala en el remoto. |
| **Rama** | Cada tarea sube su propia rama `sb/<job>` para que la revises y fusiones. Las demás tareas empiezan desde la rama principal del proyecto. |

Cada máquina usa el remoto y las credenciales de Git del propio repositorio. Antes de iniciar una tarea, obtiene la rama principal remota y adelanta su copia local por fast-forward si es posible. Si falla una subida, abre el **Informe de entrega** de la tarea para ver el motivo, la rama local, el commit y el comando de subida. [Buscar la entrega de una tarea](jobs.md)

## Añadir, mover o quitar una máquina

En **Detalles del equipo**, abre **Lista de máquinas** y usa el botón más para **Añadir una máquina**. Selecciona una máquina vinculada y elige **Igual que la carpeta del equipo** o introduce su propia ruta absoluta en **Carpeta del proyecto**. Puedes editar esa ruta más adelante. Una máquina apta con capacidad libre ya puede recoger una tarea de la misma cola.

Para quitar una máquina del equipo, selecciónala y confirma **Quitar del equipo**. Dejará de tomar tareas nuevas de esta cola. Si quitas o retiras la máquina marcada con **El líder se ejecuta aquí**, la máquina restante que se unió primero al equipo asume el papel de líder. No se permite quitar la última máquina del equipo. Añade primero su sustituta.

## Configurar cómo asume tareas el equipo

Vuelve a **Detalles del equipo** para cambiar cómo trabaja el equipo.

- En **Configuración de tareas**, **Reparto** controla el trabajo nuevo. Elige **En pausa** para retener las tareas en cola mientras las que están en curso continúan. Elige **Normal** para que las máquinas vuelvan a tomar tareas de la cola.
- **Trabajos simultáneos** tiene como valor predeterminado **Sin límite**, por lo que se aplica el límite de concurrencia de tu cuenta. Elige **Fijar un número** para limitar las tareas en curso de este equipo. Una reducción se aplica a medida que terminan las tareas en curso.
- En **Modelo del Líder**, selecciona la cuenta y luego el modelo y el nivel de esfuerzo si se ofrece. La lista muestra cada cuenta con su máquina. Si eliges una cuenta de otra máquina del equipo, el líder pasa a esa máquina para el mensaje siguiente. Usa el mismo resumen de la conversación y la misma memoria del equipo. Las tareas en curso permanecen en sus máquinas.
- Para los trabajadores, elige el modelo preferido y, cuando se ofrezca, el esfuerzo para cada nivel de dificultad y proveedor. **Restaurar predeterminado** restituye el valor predeterminado del equipo para esa opción. En **Lista de cuentas** puedes reservar una cuenta para escritura, revisión o el líder. [Cuentas de motores y ritmo](engine-accounts-and-pacing.md)

## Disolver un equipo

Abre **Detalles del equipo**, elige **Disolver equipo**, comprueba cuántas sesiones de agents terminarán y escribe el nombre del equipo para confirmar. La disolución es permanente. Cancela las tareas abiertas, borra los eventos programados y quita el equipo de tu lista y de los accesos al chat. Terminan sus solicitudes de sesiones de agents pendientes y sus sesiones activas. Cada participante conserva el historial de su sesión. Las máquinas siguen vinculadas a tu cuenta.

## Si algo falla

- Si no hay ninguna máquina que seleccionar, elige **Vincular máquina** al crear un equipo o **Vincular una nueva máquina** al añadir una. Si la máquina se retiró, vuelve a vincularla antes de añadirla.
- Si una tarea o el chat indica que no se puede crear el directorio, comprueba la ruta en la máquina que intentó usarla. Un archivo en esa ruta, la falta de permiso de escritura o un disco de solo lectura pueden impedir la creación. Elige **Cambiar el directorio en los ajustes del equipo** e introduce un directorio en el que se pueda escribir en esa máquina.
- Si la cuenta o el modelo del líder deja de estar disponible durante la creación, elige de nuevo en la lista actualizada. Si tras la creación hay trabajo esperando en la cola, consulta **Por qué no está en curso** en los detalles de la tarea para ver si la retienen el reparto, un límite o una cuenta.
