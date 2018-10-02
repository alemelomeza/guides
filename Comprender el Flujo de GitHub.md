# Comprender el flujo de GitHub Flow

GitHub Flow es un flujo de trabajo ligero y basado en ramas que adminte equipos y proyecto donde las implementaciones se realizan con regularidad. Esta guía explica cómo y por qué funciona GitHub Flow.

## Crear una rama

Cuand trabaje en un proyecto, tendrá varias funciones o ideas en progreso en un momento dato, algunas de las cuales están listas para comenzar y otras que no. Existe una ramificación para ayudarlo a administrar este flujo de trabajo.


Cuando creas una rama en tu proyecto, estás creando un entorno donde puedes probar nuevas ideas. Los cambios que realice en una rama no afectan a la rama principal o maestra, por lo que puede experimentar y realizar cambios de forma libre, con la certeza de que su rama no se fucionará hasta que esté lista para ser revisada por alguien con quien esté colaborando.

### ProTip

La ramificación es un concepto conetral en Git, y todo el flujo de GitHub se basa en él. Solo hay una regla: cualquier elemento en la rama principal siempre se puede desplegar.

Debido a esto, es extemadamente importante que su nueva rama se cree fuera de la principal cuando se trabaja en una característica o solución. El nombre de su rama debe ser descriptivo (por ejemplo, refactor-authentiction, user-content-cache-key, make-retina-avatars), para que otros puedan ver en qué se está trabajando.

## Agregar confirmaciones (commits)

Una vez que se haya creado su rama, es hora de comenzar a hacer cambios. Cada vez que se agregue, edite o elimine un archivo, realizará una confirmación y los agragará a su rama. Este proceso de agregar confirmaciones realiza un seguimineto de  su progreso a medida que trabaja en una rama de características.

Las confirmaciones también crean una historia transparente de su trabajo que otros pueden seguir para comporender lo que ha hecho y por qué. Cada confirmación tiene un mensaje asociado, que una descripción que explica por qué se realizó un cambio en particular. Además, cada confirmación se considera una unidad de cambio separada. Esto le permite deshacer los cambios si se encuentra un error o si deside dirigirse en una dirección diferente.

### ProTip

Los mensaje de confirmación son importantes, especialmente porque Git rastrea los cambios y luego los muestra como confirmaciones una vez que se envían al servidor. Al escribir mensajes claros de confirmación, puede hacer que sea más fácil para otras personas seguir y proporcionar comentarios.

## Abrir solicitud de extracción (pull request)

Las solicitudes de extracción inicia la discución sobre sus confirmaciones. Debido a que están estrechamente integrados con el repositorio de Git subyacente, cualquiera puede ver exactamente qué cambios se fusionarían si aceptan su solicitud.

Puede abrir una solicitud de extracción en cualquier momento durante el proceso de desarrollo: cuando tien poco o ningún código pero desea compartir algunas capturas de pantalla o ideas generales, cuando está atascado y necesita ayuda o consejo, o cuando está listo para que alguien revise su trabajo. Al usar el sistema @mención de GitHub en su mensaje de solicitud de extracción, puede solicitar comentarios de personas o equitpos expecíficos, ya sea que estén al final del pasillo a diez zonas horarias de distancia.

### ProTips

Las solicitudes de extracción son útiles para contribuir a proyectos de código abierto y para administrar cambios en repositorios compartidos. Si está utilizando un modelo Fork & Pull, las solicitudes de extracción proporcionan una forma de notificar a los responsables del proyecto sobre los cambios que desea que consideren. Si está utilizando el modelo de Shared Repository, las solicitudes de extracción ayudan a iniciar la revisión del código y la conversación sobre los cambios propuestos antes de que se fusionen en la rama pricipal.

## Discute y revisa tu código

Una vez que se ha abierto una solicutud de extracción, la persona o el equipo que revisa sus cambios puede tener preguntas o comentarios. Tal vez el estilo de codificación no coincida con las directrices del proyecto, al cambio le faltan pruebas unitarias, o tal vez todo se ve bien y en orden. Las solicitudes de extracción están diseñadas para alentar y capturar este tipo de conversación.

También puede seguir subiendo cambios a su rama a la luz de la discusión y comentarios sobre sus confirmaciones. Si alguien comenta que olvidó hacer algo o si hay un error en el código, puede solucionarlo en su rama y haer subir el cambio. GitHub mostrará tus nuevas confirmaciones y cualquier comentario adicional que recibas en la vista de solicitud de extracción unificada.

### ProTip

Los comentarios de la solicitud de extreacción se escriben en Markdown, por lo que puede incrustar imágenes y emojis, usar bloques de texto preformateados y otros formatos ligeros.

## Desplegar

Con GitHub, pude implementar desde una rama para pruebas finales en producción antes de fucionarse con la principal.

Una vez que su solicitud de extracción ha sido revisada y la rama aprueba sus pruebas, puede implementar sus cambios para verificarlos en producción. Si su rama causa problemas, puede deshacerla desplegando la principal existente en producción.


## Unir

Ahora que sus cambios han sido verificados en producción, es hora de fusionar su código en la rama principal.

Una vez fusionadas, las solicitudes de extracción conservan un registro de los cambios históricos en su código. Como puede buscarse, permiten que alquien retroceda en el tiempo para comprender por qué y cómo se tomó una desición.

### ProTip

Al incorporar ciertas palabras clave en el texto de su solicitud de extracción, puede asociar problemas con el código. Cuando su solicitud de extracción se fusiona, los problemas relacionados también se cierran. Por ejemplo, ingresar la frase `close #32` cerraría el número 32 en el respositorio. Para obtener más información.
