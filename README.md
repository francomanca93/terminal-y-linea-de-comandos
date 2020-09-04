
<div align="center">
    <h1>Introducción a la Terminal y Línea de Comandos</h1>
    <img src="readme_img/terminal.png" width="">
</div>

## Introducción al documento

El contenido de este documento son **apuntes teoricos y prácticos** del [Curso de Introducción a la Terminal y Línea de Comandos](https://platzi.com/cursos/terminal/) y busca ser una guía para futuros trabajos personales. El mismo está dictado por [Mauro Chojrin](https://twitter.com/mchojrin), consultor PHP en [Leeway academy](https://academy.leewayweb.com/). El curso es de [Platzi](https://platzi.com).

El curso se explorará la terminal y como esta optimiza la navegación y ejecución de programas en sistemas operativos Unix. Conociendo y dominando la terminal, se podrá invocar y ejecutar programas, crear directorios de los mismos y navegar en ellos de una manera veloz y eficiente.

## Objetivos del documento

- Aprender a usar la terminal desde cero.
- Domina la interfaz de comandos de la terminal.
- Listar archivos y directorios en la terminal.
- Automatizar tareas con la terminal de comandos.
- Comprender los mecanismos de comunicación y administración entre procesos.
- Administra tus archivos desde la terminal.

## Tabla de contenido

- [Curso de Introducción a la Terminal y Línea de Comandos](#curso-de-introducción-a-la-terminal-y-línea-de-comandos)
  - [Comprender las ventajas del uso de la terminal](#comprender-las-ventajas-del-uso-de-la-terminal)
    - [Introducción al curso: ¿Qué es y cómo funciona la terminal?](#introducción-al-curso-qué-es-y-cómo-funciona-la-terminal)
  - [Aprender a manipular archivos a través de la terminal](#aprender-a-manipular-archivos-a-través-de-la-terminal)
  - [Comprender los mecanismos de comunicación y administración entre procesos](#comprender-los-mecanismos-de-comunicación-y-administración-entre-procesos)
  - [Conocer herramientas avanzadas](#conocer-herramientas-avanzadas)
  - [Automatizar tareas: el verdadero poder de la terminal](#automatizar-tareas-el-verdadero-poder-de-la-terminal)

# Curso de Introducción a la Terminal y Línea de Comandos

## Comprender las ventajas del uso de la terminal

### Introducción al curso: ¿Qué es y cómo funciona la terminal?

- **Terminal y Línea de comandos**

[Interfaz de línea de Comandos](https://es.wikipedia.org/wiki/Interfaz_de_l%C3%ADnea_de_comandos) es un método que permite a los usuarios dar instrucciones a algún programa informático por medio de una línea de texto simple.

> NOTA: CLI = Command Line Interface

La [terminal](https://es.wikipedia.org/wiki/Emulador_de_terminal) es un programa informatico que nos permite comunicarnos con la computadora y poder realizar tareas especificas mediante una interfaz de texto. Utiliza un entorno 100% texto por lo tanto es muy eficiente y podemos automatizar tareas.

- **Los Comandos**

Orden o instrucción para el sistema. Suele admitir parámetros o modificadores/argumentos.

Su estructura esta dada por: `nombre_de_comando parametro modificadores`

Un comando consiste en: `comando -flag1 -flag2 arg1 arg2`

- **Comando**: Nombre de un programa. `comando`
- **Parametros**: Los parametros son información adicional para la ejecución del programa. `-flag1 -flag2`
- **Modificadores**: Alteran lo que el programa va a hacer. `arg1 arg2`

Algunos comando son:

- `date`: Muestra la fecha
- `echo`: permite imprimir en la terminal (Como PHP)
  - `echo "Hola mama estoy en el terminal"`
- `man`: (de manual) muestra información sobre otros comandos.
  - `man date`: Muestra informacion sobre otros comandos.

Utilidades del CLI: Combinaciones de teclas y sustitución de comandos comodines.

Ejemplos:

- Si escribimos `ma` y luego teclamos la tecla `“TAB”`, nos mostrara todos los comandos que comiencen por **‘ma’**.
- `Flecha para arriba`: podemos observar los comandos que ya hemos escritos.
- `CTRL+SHIFT+R`: funciona como buscador, para ver si hemos teclado algún comando.
- `history`: Podemos ver todos los comandos que escribimos alguna vez. Podemos volver a ejecutaralgunos de esos comandos si escribimos (!) seguido del nùmero indice del listado.
  - `!numero_indice_del_listado`: `!475`

## Aprender a manipular archivos a través de la terminal

## Comprender los mecanismos de comunicación y administración entre procesos

## Conocer herramientas avanzadas

## Automatizar tareas: el verdadero poder de la terminal
