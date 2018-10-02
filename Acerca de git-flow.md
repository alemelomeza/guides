# Flujo de trabajo con git flow

Vincent Driessen define git flow como una colección de extensiones de Git que nos facilita un conjunto de operaciones de alto nivel para trabajar con las siguientes ramas:

* __master__: es la que contiene la última vesión de nuestro proyecto y usaremos para desplegar en __producción__.
* __develop__: es la que contiene el último estado del desarrollo del mismo, es decir, hasta el último commit que hayamos hecho.
* __feature__: se usarán para desarrollar nuevas funcionalidades, se crearán a partir de la rama develop y al terminar con esta funcionalidad nueva, se tiene que fusionar otra vez con __develop__.
* __release__: se usarán para lanzar una nueva versión de nuestro proyecto. Se usarán solo para los últimos retoques antes de liberar la nueva vesión, como cambiar el número de esta, y crearán a partir de la rama __develop__ y se fusionara tanta con __master__ (para poder ser desplegadas en producción) como con __develop__.
* __hotfix__: se usarán para esos cambios rápidos que queremos realizar como arreglar un bug sencillo en producción mientras que al mismo tiempo estamos desarrollando una nueva funcionalidad y queremos desplegar este arreglo lo antes posible. Se crean a partir de la rama __master__ y se fusionan con __master__ y __develop__.

Una vez instalado y desde el directorio raiz de nuestro proyecto, tenermos que inicializarlo:


```
$ git flow init
```

Esto nos hará una serie de preguntas sobre como queremos nombrar a las diferentes ramas y el prefijo de nuestras versiones. Si queremos usar las de estan por defecto, pulsamos enter en todas las opciones o podemos usar esta instrucción para inicializarlo:

```
$ git flow init -d
```

Ahora ya tenemos creada nuestra rama __develop__ y estamos listos para empezar a trabajar.

## Trabajando con features

Para empezar a desarrollar una nueva funcionalidad tenemos que crearla usando:

```
$ git flow feature start nombre_de_funcionalidad
```

Automáticamente crea la rama feature/nombredefuncionalidad y posiciona en ella. Ahora después de varias confirmaciones (commits) puedes cerrarla usando:

```
$ git flow feature finish nombre_de_funcionalidad
```

Si en algún momento queremos ver que ramas de __features__ tenemos actualmente, podemos hacerlo usando:

```
$ git flow feature
```

Si quisiéramos remotar una de esas funcionalidades que estamos realizando, por ejemplo después de solucionar un __hotfix__, podemos hacerlo usando:

```
$ git flow feature checkout nombre_de_funcionalidad
```

## Trabajo con releases


Para liberar una nueva versión de nuestro proyecto tenemos que crearla usando:


```
$ git flow release start version_1
```

Ahora después de varias confirmaciones (commits) puedes cerrarla usando:

```
$ git flow release finish version_1
```

Esto buscará cambios en nuestro repositorio remoto, fusionará esta versión con nuestras ramas __master__ y __develop__, borrando la __release__ y dejándonos todo listo para desplegar desde la rama __master__.

## Trabajando con hotfixes

Si trabajamos en una funcionalidad y tenemos que cambiar algo que no funciona bien en nuestro entorno de producción, crearemos una rama __hotfix__ usando:

```
$ git flow hotfix start error_en_produccion
```

Esta rama será creada a partir de la rama __master__, ya que es lo último que hemos desplegado. Al arreglar el problema podemos usar:

```
$ git flow hotfix finish error_en_produccion
```

Esto fucionará los cambios tanto con __develop__ como con __master__, teniendo la solución al problema listo para ser desplegado en producción.

Git Flow automatiza muy bien la manera de trabajar con Git, aplicando un flujo de trabajo probado, que se adapta perfectamente a la mayoría de proyectos.
