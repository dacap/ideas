# Ideas
> Ideas sobre software, hardware y cualquier otra cosa. <br>
> (C) 2014 David Capello

## Sobre lenguajes de programación

### Lenguaje sencillo de aprender

Que no sea radicalmente distinto a lo ya conocido, pero que tenga
conceptos más fáciles de aprender, sin perder análisis estático,
agilidad de desarrollo, y posibilidad de optimización. Lo más cercano:
[Quorum](http://quorumlanguage.com)

### Lenguaje de dominio HTML

JavaScript no conoce nada sobre la web. Deberíamos crear un lenguaje
de programación que entienda sobre los conceptos que rodean la
web. Algo así como un *domain-specific language*. Del mismo modo que
SQL es específico para bases de datos relacionales, este nuevo
lenguaje debería ser específico para la web.

*¿Por qué no JavaScript?* Mi pregunta es por qué deberíamos de
escribir `"<b>" + texto + "</b>"` alguna vez.

### Un no-lenguaje de programación (manipulación de árboles AST)

(Continuar aquí.)

## Sobre UI/UX

### Librería de layout

Crear una librería genérica de layout en C++ --independiente de la
plataforma-- que sirva para acomodar elementos gráficos en la pantalla
según el tamaño de la ventana, algo así como *responsive design for
desktop*.

Luego podrían existir conectores entre la librería de layout genérico
y un acomodador de ventanas/controles de: HWND crudos, controles Qt,
wxWidgets, Gtk+, etc. Inclusive se podría usar como layout de
elementos del DOM al compilar la librería con emscripten.

## Sobre duplicación de código

### Repositorio universal de librerías

Hacer una organización en GitHub donde cada repositorio es una
micro-librería para hacer una tarea particular. (Ejemplos: recorrer
directorios, leer un archivo XML, el algoritmo *quicksort*, etc.)
Existirían repositorios como `fs-source` que representarían la
librería para manejar el *file system* en un pseudo lenguaje de
programación (identificado como `source` aquí). Luego, se generarían
repositorios como `fs-cpp`, `fs-java`, `fs-python`, etc. que serían
versiones del código original convertidos
automáticamente/periódicamente/por-comit desde `fs-source` a C++,
Java, Python, etc.
