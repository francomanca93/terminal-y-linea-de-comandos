
<div align="center">
    <h1>Introducción a la Terminal y Línea de Comandos</h1>
    <img src="readme_img/terminal.png" width="">
</div>

## Tabla de contenido

- [Curso de Introducción a la Terminal y Línea de Comandos](#curso-de-introducción-a-la-terminal-y-línea-de-comandos)
  - [Primeros pasos](#primeros-pasos)
    - [¿Qué es la terminal?](#qué-es-la-terminal)
    - [Aprendiendo a caminar en la terminal](#aprendiendo-a-caminar-en-la-terminal)
      - [Comandos Basicos de la terminal](#comandos-basicos-de-la-terminal)
    - [Manipulando archivos y directorios](#manipulando-archivos-y-directorios)
      - [Explicacion detallada de la importancia de `rm`](#explicacion-detallada-de-la-importancia-de-rm)
    - [Explorando el contenido de nuestros archivos](#explorando-el-contenido-de-nuestros-archivos)
    - [¿Qué es un comando?](#qué-es-un-comando)
    - [Wildcards](#wildcards)
  - [Empezando a correr](#empezando-a-correr)
    - [Redirecciones: cómo funciona la shell](#redirecciones-cómo-funciona-la-shell)
    - [Redirecciones: pipe operator](#redirecciones-pipe-operator)
    - [Encadenando comandos: operadores de control](#encadenando-comandos-operadores-de-control)
    - [Cómo se manejan los permisos](#cómo-se-manejan-los-permisos)
    - [Modificando permisos en la terminal](#modificando-permisos-en-la-terminal)
    - [Cómo configurar variables de entorno](#cómo-configurar-variables-de-entorno)
    - [Comandos de búsqueda](#comandos-de-búsqueda)
    - [Su majestad: grep](#su-majestad-grep)
  - [Utilidades de la terminal](#utilidades-de-la-terminal)
    - [Utilidades de red](#utilidades-de-red)
    - [Comprimiendo archivos](#comprimiendo-archivos)
    - [Manejo de procesos](#manejo-de-procesos)
    - [Procesos en foreground y background](#procesos-en-foreground-y-background)
    - [Editores de texto en la terminal](#editores-de-texto-en-la-terminal)
    - [Personalizar la terminal de comandos](#personalizar-la-terminal-de-comandos)

# Curso de Introducción a la Terminal y Línea de Comandos

## Primeros pasos

### ¿Qué es la terminal?

La terminal es una herramienta indispensable que cualquier persona en la tecnología debe conocer 👀. Es importante porque:

- Te da **flexibilidad** 📏. Con unos pocos comandos, puedes hacer mucho.
- Es mucho más **veloz** que una interfaz 💻.
- Es tu única opción si no hay interfaz 😆, como para **configurar un servidor** remoto.
- Puedes invocar **demonios** 👿. Hay que tener cuidado con los comandos.

Específicamente, la terminal es una interfaz gráfica muy sencilla que simula una línea de comandos:

- **Terminal**: Ventana que muestra el prompt. **Prompt** es el carácter o conjunto de caracteres que se muestran en una línea de comandos para indicar que está a la espera de órdenes. Este puede variar dependiendo del intérprete de comandos y suele ser configurable.
- **Shell (línea de comandos)**: Programa que ejecuta los comandos. Hay varios tipos de shell, pero sirven para lo mismo. La más comunes son **bash shell** o **Z shell**. En este curso, usaremos la primera 🍎.

Para conocer que shell tenemos:

- `$ echo $SHELL`

> Un comando es un programa que se puede ejecutar desde la terminal.

### Aprendiendo a caminar en la terminal

Debemos entender como esta compuesto el sistema de archivos de linux, en la siguiente imagen podemos ver un arbol de la composición:

![sistema-de-archivos-linux](https://i.imgur.com/iKZ1zGJ.png)

En el siguiente gráfico tenemos un detalle mas amplio de lo que tenemos en el sistema de archivos de Linux.:

![sistema-de-archivos-linux-detalles](https://i.imgur.com/uAGsiOD.png)

#### Comandos Basicos de la terminal

- `ls`: Listar archivos
- `ls -lh`: Listar archivos para ver su peso de una manera mas legible
- `ls -a`: Listar archivos ocultos
- `pwd`: Identificar la ruta en la que estamos en nuestro sistema
- `cd`: Movernos entre directorios
- `mkdir`: Crear un directorio
- `cp`: Copiar un archivo
- `rm`: Borrar un archiv
- `mv`: Mover un archivo
- `rmdir`: Borrar un directorio:
- `clear` o `Ctrl + L`: Limpiar la terminal

### Manipulando archivos y directorios

Manipular archivos

- `ls`: Algunas variantes:
  - `ls -la`: Nos muestra todo, incluso los ocultos.
  - `ls -lS`: Los ordena por tamaño.
  - `ls -lr`: Los muestra en reversa.

- `tree`: Nos muestra todo, lo que hay dentro de cada carpeta, en forma de arbol 🌲. Podemos elegir el nivel de profundidad con `tree -L <numero de niveles>`

- `mkdir <nombre_directorio>`: crea un directorio también puedes añadir la ruta

- `touch <nombre_archivo>`: crea un archivo, si no indicas la extension por defecto sera .txt

- `cp <archivo> <ruta>`: nos permite duplicar archivos, para duplicar directorios con su contenido añadir el modificador `-r` que indica recursividad

- `mv <archivo> <ruta>`: mover un archivo hacia un directorio. También se usa para renombrar archivos `mv <archivo> <nuevo nombre>` no olvidar la extension del archivo. Para mover directorios añadir el modificador `-r`.

- `rm <archivo>`: Elimina archivos. Hay una opción muy útil que es `rm -i <archivo>(interactivo)` que te pregunta explícitamente si en verdad si quiere borrarlo 😟. Funciona de manera directa para directorios vacíos, pero si hay archivos dentro, debes usar la opción recursiva `rm -r <directorio>`, que lo que hace es ir borrando todo lo que hay dentro y al final borra el directorio 🔫. Te va preguntando por cada cosa.

> Ojo: Lo que borras desde la terminal se borra para siempre 😟.

#### Explicacion detallada de la importancia de `rm`

**¿Y para qué me sirve correrlo como interactivo?**

Si te preguntaste esto es porque seguramente aún no te has dado cuenta de lo peligroso que es eliminar algo. Cuando tú eliminas algo desde la terminal, este archivo/carpeta se elimina… **PARA SIEMPRE *chan, chan chan*.**

Con esto me refiero a que ese archivo que eliminaste NO se va a mover al basurero, sino que directamente se va a eliminar, y la única forma de recuperarlo podría ser con algún programa que lea sector por sector de tu disco duro.

Sobre cómo eliminar una carpeta, el comando que más comparten es `rm -rf` carpeta sin saber exactamente qué es lo que hace, poner esa `f` como parámetro es muy peligroso. Con poner `f` basta, esto porque el borrado es recursivo básicamente recorrerá cada subcarperta/archivo y las irá borrando uno por uno.

**#################################**
**DANGER ZONE**
**#################################**

Ahora quiero explicarte por qué este comando es peligroso, tanto que puedes llegar a eliminar tu sistema operativo, **NO CORRAS ESTE COMANDO POR NADA DEL MUNDO.**

Imagina que quieres eliminar alguna carpeta de tu computadora usando la terminal, y por alguna razón decides usar una ruta absoluta:

`rm -rf / home/tuUsuario/carpetaAEliminar/`

Todo bien… ¿verdad? Bien, si ejecutaras este comando todo tu sistema operativo desaparecería, ¿por qué? quiero que te fijes cómo entre el `/` y la palabra `home` hay un espacio… ¿recuerdas qué significaba esa `/`? Es la carpeta **raíz**, la carpeta **donde vive todo tu sistema operativo**, y le estás diciendo que la elimine a la fuerza, ese espacio indica que va a eliminar dos carpetas, primero eliminará `/` y luego eliminará `home/tuUsuario/carpetaAEliminar/`.

El comando correcto que deberíamos usar es:

`rm -rf /home/tuUsuario/carpetaAEliminar/`

Aquí ese espacio no existe, por lo que todo iría bien, quiero que te fijes cómo con un pequeño error, puedes eliminar todo. Por eso siempre ten cuidado al usar este comando, y de preferencia… **¡Usa el modo interactivo! 😄**

### Explorando el contenido de nuestros archivos

Podemos explorar el contenido de archivos sin la necesidad de abrirlos, desde la terminal 🧐. Esto para archivos de texto.

- `cat <documento de texto >`: Nos muestre el documento de texto completo.
- `head <documento de texto>`: Nos muestra las primeras 10 líneas de un archivo de texto. Para especificar el número de líneas `head -n <numero de lineas> <archivo>`.
- `tail <documento>`: Nos muestra las últimas 10 líneas.

![cat-head-tail-commands](https://i.imgur.com/y0eTRIJ.png)

- `less <archivo>`: Este es muy cool, es muy interactivo, nos permite hacer scroll, y nos permite hacer búsquedas haciendo `/<palabra a buscar>`. Para salir presionamos `q` 🔍.
- `xdg-open <archivo>`: Para abrir un archivo desde la terminal. Usa las aplicaciones predeterminadas. Esto para linux, para mac, es `open`. Esto crea un proceso en la terminal que no nos dejará hacer nada mas. Para terminar el proceso `ctrl+c`.
- `nautilus` nos permite abrir el explorador de archivos en una posición dada (en linux) 📁.

### ¿Qué es un comando?

Un comando puede ser 4 cosas:

- Un programa ejecutable que se compilo en algun lenguaje de programación y se puede ejecutar.
- Un comando de utilidad de la shell.
- Una función de shell
- Un alias

Comandos

- `type` nos permite saber que clase es un comando. Por ejemplo `type cd` (es una funcion de shell), `ls` (es un alias). Ejemplos:

```txt
$ type cd
cd is a shell builtin

$ type mkdir
mkdir is hashed (/usr/bin/mkdir)

$ type ls
ls is aliased to `ls --color=auto'
```

- Para crear un alias: `alias ‘nombreDelAlias’ = ‘comandoQueInvoca’`. Por ejemploalias `l=”ls -lh”`. Temporales, se borra cuando cerramos la terminal.
- Con `–help` o `help`, puedes tener una ayuda sobre los comandos.
- `man ‘comando’` : hace referencia al manual de usuario de un comando, otro similar es `info 'comando'`.
- `whatis ‘comando’`: nos da una descripcion muy corta de que hace ese comando. Pero no funciona con todos.

### Wildcards

Son una serie de caracteres especiales que nos permiten realizar búsquedas muy avanzadas utilizando `ls` 🔍. Puedes utilizar wildcards con otros comandos que realicen manipulación de archivos como `mv`, `cp` o `rm` 💫. También se conocen como **comodines**.

- `ls *.txt`: Lo que hace este comando es listar todos los archivos que tengan extensión .txt, independientemente del nombre que tengan.
- `ls datos*`: Lo que hace este comando es listar todos los archivos que inicien con la palabra “datos”, independientemente de cómo siga el nombre o la extensión que tenga.
- `ls datos?`: Lo que hace este comando es listar todos los archivos que inicien con la palabra “datos” y solamente tengan un caracter más luego de esa palabra.
- `ls datos???`: Lo que hace este comando es listar todos los archivos que inicien con la palabra “datos” y solamente tengan tres caracteres más luego de esa palabra.
- `ls [[:upper:]]*`: Lo que hace este comando es listar todos los archivos que inicien con una mayúscula, independientemente de cómo siga el nombre o la extensión que tenga.
- `ls -d [[:upper:]]*`: Lo que hace este comando es listar todos los DIRECTORIOS que inicien con una mayúscula, independientemente de cómo siga el nombre que tenga.
- `ls [[:lower:]]*`: Lo que hace este comando es listar todos los DIRECTORIOS que inicien con una minúscula, independientemente de cómo siga el nombre o la extensión que tenga.
- `ls [ad]*`: Lo que hace este comando es listar todos los archivos que inicien con la letra “a” o con la letra “d”, independientemente de cómo siga el nombre o la extensión que tenga.

## Empezando a correr

### Redirecciones: cómo funciona la shell
### Redirecciones: pipe operator
### Encadenando comandos: operadores de control
### Cómo se manejan los permisos
### Modificando permisos en la terminal
### Cómo configurar variables de entorno
### Comandos de búsqueda
### Su majestad: grep

## Utilidades de la terminal
 
### Utilidades de red
### Comprimiendo archivos
### Manejo de procesos
### Procesos en foreground y background
### Editores de texto en la terminal
### Personalizar la terminal de comandos