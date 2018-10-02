## Acerca de git-flow

git-flow es un conjunto de extensiones para git que proveen comandos de alto nivel para operar repositorios basados en el modelo de ramificaciones de Vincent Driessen.

Este documento de referencia explica las operaciones básicas de git-flow, los comandos y sus efectos.

## Conseptos básicos

* git-flow provee una excelente ayuda en línea de comandos e información. Leé con atención lo que sucede.
* git-flow funciona básandose en fusiones de ramas (_merge_). No reorganiza (_branch rebase_) las ramas de características (_feature branches_).

## Configuración

* Un prerequisito es una intalación de git en funcionamiento.
* git-flow funciona en OSX, Linux y Windows.

__OSX__:

```bash
$ brew install git-flow-avh
```

__Linux__:

```bash
$ apt-get install git-flow
```

__Windows__:

```bash
C:\> choco install git-flow-avh
```

## Introducción

git-flow necesita ser inicializado para poder alterar la configuración del proyecto.

### Inicialización

Comience con usar git-flow inicializándolo desde dentro de un repositorio git existente:

```
git flow init
```

Deberá contestar algunas preguntas relacionadas con las convenciones de nombres para las ramas. Se recomienda utllizar los valor predeterminados.

## Carácteristicas

* Desarrollar características para futuras versiones.
* Es típico que sóllo se use en los repositorios para desarrollo.

### Comenzar una nueva característica

El desarrollo de nuevas características  parte de la rama __develop__.

Comienze con una nueva característica usando:

```
git flow feature start mi_caracteristica
```

Esta acción  crea una nueva rama derivada de __develop__ y salta a esta, estableciéndola como rama de trabajo actual.

### Finalizar una característica

Finaliza el desarrolo de una característica. Esta acción realiza lo siguiente:

* Fusiona _mi_caracteristica_ en __develop__.
* Borra la rama _mi_caracteristica_.
* Salta a la rama __develop__, estableciéndola como rama de trabajo actual.

```
git flow feature finish mi_caracteristica
```

### Publicar una característica

¿Estás trabajando colaborativamente? Publica una característica a un servidor remoto para que así puede ser vista otros.

```
git flow feature publish mi_caracteristica
```

### Obeniendo características publicadas

Obtiene una característica publicada por otro y mantiene un seguimiento de sus cambios.

```
git flow feature pull mi_caracteristica
```

## Publicar una versión

* Prepara una versión para producción.
* Permite arreglos menores y la preparación de los metadatos para la publicación.

### Comenzar una publicación

Para comenzar una publicación, usa el comando `git-flow release`. Creará una rama de publicacón derivada de la rama __develop__.

```
git flow release start version!.0.0 [base]
```

Opcionalmente, puede usar `[base]` indicando el código sha-1 del cambio desde el cual comenzar la versión  de publicación. El cambio deber, ser parte de la rama __develop__.

Es apropiado publicar remotamente la rama de publicación después de crearla para permitir que otros desarrolladores envíen cambios para esta versión. Hazlo de forma similar a publicar características:

```
git flow release publish version1.0.0
```

(Pude establecer el seguimiento de los cambios de la publicación remota utilizando el comando `git flow release track version1.0.0`)

### Concluir una publicación

Dar cierre a una publicación es una gran paso. Realiza varias acciones:

* Fusiona la rama de la publicación con la rama __master__.
* Etiqueta el cambio con su nombre
* Vuelve a fusionar la publicación con la rama __develop__.
* Borrar la rama de la publicación.

```
git flow release finish version1.0.0
```

## Revisiones

* Las revisiones surgen de la necesidad de actuar inmediatamente cuando la versión ejecutándose en producción se encuentra en un estado que no deseamos.
* Puede ramificarse desde la versión correspondiente etiquetada en la rama __master__ que corresponde a la versión en producción.

### Comensar un revisión

Como otros comandos de git-flow, una revisión se abre con:

```
git flow hotfix start version1.0.1 [basename]
```

El argumento de la versión determina el nombre de la revisión. Opcionalmente, puede agregar un nombre para la base desde la cual comenzar.

### Cerrar una revisión

Al cerrar un revisión, esta se fusiona con las ramas __develop__ y __master__. Luego, el cambio en __master__ es etiquetado con el nombre de la revisión.

```
git flow hotfix finish version1.0.1
```

![commandos git-flow](images/acerca_de_git-flow_img1.png)