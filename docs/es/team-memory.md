[← SailorBridge](README.md)

# Memoria del equipo

La memoria del equipo guarda decisiones, convenciones y correcciones que tu **Líder** y los trabajadores pueden reutilizar en tareas futuras. Cada entrada tiene un título, un contenido, una fuente y un número, como `#6`. La entrada pertenece a un solo equipo. Los demás equipos y tus amigos no pueden consultarla.

## Guardar algo que merezca recordarse

En el chat del equipo, di qué quieres que recuerde y cuándo se aplica. Por ejemplo, «Recuerda que los ejemplos de instalación van en la guía de configuración. Úsala al cambiar un comando de instalación». El **Líder** te dice qué ha guardado. Abre el menú **Más acciones** del chat del equipo y elige **Memoria del equipo** para ver la entrada. Abre el título para leer el texto completo y ver quién lo modificó por última vez.

## Encontrar una entrada y usarla en el chat

Abre **Buscar** en **Memoria del equipo**. Escribe palabras del título o del contenido. Para un resultado textual deben coincidir todas las palabras. La primera página también puede mostrar hasta tres entradas de significado similar. Las entradas fijadas aparecen primero en la lista normal.

Si sabes el número, busca `#6` para obtener solo la entrada 6. La búsqueda de `6` también encuentra coincidencias en el texto. Abre la entrada y elige **Ir al Chat**. El campo de texto contiene ahora `/memory #6`. Añade una pregunta o corrección y envíala.

## Editar, fijar, bloquear o eliminar una entrada

- Abre la entrada, cambia **Contenido** y elige **Guardar**. **History** muestra las últimas 10 versiones. Consulta **Observed** y **Expires** si los datos pueden cambiar. Una entrada marcada como **Expired** se puede seguir leyendo. Comprueba si lo que dice sigue siendo válido.
- Activa **Fijada** para incluir una instrucción en la información que reciben el **Líder** y los trabajadores. La entrada muestra cuánto espacio usa el equipo para lo fijado. Los títulos y contenidos fijados pueden ocupar hasta 8 KiB en total.
- Activa **Bloqueada** si quieres ser la única persona que pueda cambiar o eliminar la entrada. Si solo la fijas, los agents aún pueden editarla. Puedes editar una entrada bloqueada en la web.
- Elige **Eliminar** y confirma para eliminar una entrada de forma permanente. Su número no se vuelve a usar.

## Ordenar las entradas del equipo

Envía `/memory-tidy` en el chat del equipo. La tarea comprueba las entradas, marca las que merece la pena conservar, combina las relacionadas y elimina las que ya no servirán. Abre su **Informe de entrega** para ver qué hizo y qué requiere aún tu decisión. Las entradas bloqueadas permanecen en su sitio si la tarea propone eliminarlas o combinarlas.

La limpieza automática se ejecuta como máximo una vez por equipo en un periodo móvil de 24 horas si hay entradas que comprobar. Para ejecutarla solo a petición o en un horario programado, abre **Flujos del equipo**, selecciona `memory-tidy` y desactiva **Ordenar automáticamente**.

## Si algo falla

- Si al fijar una entrada se superarían los 8 KiB, se rechaza el cambio. Deja de fijar otra entrada o acorta el texto fijado y vuelve a intentarlo.
- Si alguien modificó la entrada mientras trabajabas en ella, se muestra el contenido más reciente. Léelo antes de volver a aplicar la corrección.
- Si dos actualizaciones usan el mismo título, una corrección del mismo autor puede aplicarse directamente. En los demás casos, puede decidir el nivel de confirmación más alto o, si el nivel es igual, la observación más reciente. Si las actualizaciones requieren una decisión, la entrada indica **Conflicto sin resolver** y conserva el texto actual. Ábrela, comprueba el dato y guarda la redacción correcta. Si está bloqueada, debes decidir tú.
- Si el **Líder** indica que una entrada no se guardó, repite qué quieres que recuerde. Si se rechazó el cambio de un agent porque la entrada está bloqueada, hazlo tú mismo en **Memoria del equipo**.
