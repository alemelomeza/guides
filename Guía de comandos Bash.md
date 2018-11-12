# Guía de comandos Bash

## ls

Lista los nombre de carpetas y archivos en el directorio de trabajo actual:

```$ ls -a``` enumera todos los archivos, incluidos los archios ocultos

```$ ls -A``` enumera todos los archivos, incluidos los archivos ocultos, excepto el directorio superior

```$ ls -F``` agrega un indicador (*/=>@|) a las entradas

```$ ls -S``` ordenar por tamaño de archivo

```$ ls -al``` proporciona una lista de todos los archivos en el mismo directorio

```$ ls -l``` usa un formato de listado largo

```$ ls -nl``` usa un formato de listado largo con ID de usuario

```$ ls -c``` lista contenido en columnas

## man

Es la interfaz utilizada para ver los manuales de referencia del sistem y todas las opciones disponibles para ejecutar un comando:

```$ man -``` imprime un mensaje de ayuda y sale

```$ man -V --version``` muestra información de la versión y sale

```$ man -C``` usa el archive de configuración el lugar del predeterminado en ~/.manpath

```$ man -d``` imprime información de depuración

## env

devuelve una lista de las variables de entorno para el usuario actual:

```$ env```

## chmod

Para cambiar los permisos de archivos o directorios:

```$ chmod 777``` cualquiera puede leer, escribir y ejecutar chmod 777 my_file

```$ chmod 755``` para archivos que deben ser legibles y ejecutables por otros, pero solo modificables por el usuario emisor

```$ chmod 700``` sólo el usuario puede hacer cualquier cosa al archivos


## chown

Cambia la propiedad de los archivos y directorios:

```$ chown --help && chown --version```

## path

Almacena una lista de directorios separados por dos puntos:

```$ echo $PATH```

## grep

Busca archivos en las líneas que coinciden por un patrón y devuelve los resultados:

```$ grep "keyword" file.txt``` busca la cadena dada en un solo archivos

```$ grep -i "keyword" file.txt``` permite que el comando no distinga mayúsculas de minúsculas

```$ grep -R "keyword" file.txt``` busca todos los archivos en un directorio y genera nombres de archivos y líneas que contienen resultados coincidentes

## awk

Extrae sólo una lista de cosas específicas:


```$ awk {keyword} file.txt```

## open

Abre la carpeta actual en el buscador:

```$ open .```

## chgrp

Cambia el grupo del archivo y directorio:

```$ chgrp group_name file.txt```

## pwd

Comando que imprime el nombre del directorio de trabajo:

```$ pwd```

## cd

Cambia el directorio de trabajo actual:

```$ cd /``` va al directorio raíz

```$ cd ..``` va a un directorio padre

```$ cd``` va al directorio de inicio del usuario cuando se ejecuta sin parámetro

```$ cd ~``` va al directorio de inicio del usuario cuando se le da el nombre de usuario después de "~"

## home

Muestra la ruta del directorio de inicio:

```$ echo $HOME```

## nano

Editor de texto de línea de comandos y solo acepta entrada de teclado:

```$ nane myscript.sh```

## find

Búsquedas de archivos y directorios:

```$ find directory -name filename``` busca el archovo por nombre

```$ find directory -cnewer file``` el archivo se modificó por última vez más recientemete que el archivo modificado

```$ find directory -amin n``` el archivo fue accedido por útlima vez hace n minutos

```$ find directory -cmin n``` el archivo se modificó por última vez hace n minutos

```$ find directory -atime n``` se accedió por última vez el archivo hace más n días

```$ find directory -mtime n``` los datos del archivo se modificaron hace n días

```$ find directory -ctime n``` el archivo se modificó  por última vez hace más de n días

```$ find directory -print``` muestra el nombre de la ruta de los archivos encontrados utilizando el resto de los criterios

```$ find directory -exec``` ejecuta comandos en los resultados de búsqueda resultantes

## mkdir

Crea directorios con este comando:

```$ mkdir folder``` esta comando creará las subcarpetas

## mv

Mueve un archivo o directorio como otro archivo y directorio:

```$ mv -i source``` preguntar antes de sobrescribir un archivo existente

```$ mv -f souce``` sobrescribir siempre los archivos existentes sin preguntar

```$ mv -n source``` nunca sobrescribir ningún archivo existente

```$ mv -v source``` imprimir archivos de origen y destino

## rm

Elimina objetos:

```$ rm -f file``` no hace preguntas durante la eliminación, no proporciona información para un archivo inexistente

```$ rm -i file``` pregunta antes de eliminar archivos

```$ rm -r directory``` borra el contenido de los directorios y subdirectorios consecuentemente

```$ rm -v file```proporciona información más detallada sobre el proceso de eliminación

## rmdir

Elimina el directorio, este comando solo funciona si las carpetas están vacias:


```$ rmdir -p directory_name```

##  toch

Crea o abre un archivo y lo guarda sin ningún cambio en el contenido del archivo:

```$ touch -a file``` actualiza el tiempo de acceso al archivos

```$ touch -c file``` si el archivo no existe, crea el archivos

```$ touch -m file``` cambia la hora de modificación del archivos

```$ touch -t file``` cambia el tiempo de acceso o reemplazo del archivo como se especifica

## cat

Muestra el contenido de los archivos:

```$ cat -n file``` imprime el contenido del archivo en la pantalla asignando un número a toas las líneas

## wc

Imprime recuentos de nueva línea, palabra y bytes para cada archivo, y un total si se especifica más de un archivo:

```$ wc -l``` devuelve el número de líneas

```$ wc -m file``` devuelve el número de caracteres

```$ wc -w file``` cuenta el número de palabras

## head

Muesta las primeras líneas del archivo:

```$ head file``` muestra las primeras líneas

## tail

Muesta el último par de líneas del archivo:

```$ tail file```

## more

El contenido del archivo es mostrado página a página:

```$ more file```

## less

Permite el retroceso y avance al mostrar el contenido del archivo:

```$ less file```

## nl

Agrega un número de línea por línea:

```$ nl file```
