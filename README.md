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

En
[The Future of Programming](http://pchiusano.blogspot.co.nz/2011/12/future-of-programming.html)
se habla sobre una organización del código en forma de bases de datos
relacionales. En vez de editar texto, editaríamos esta base de datos
--mediante alguna buena UI--. Así todo un nuevo conjunto de
herramientas se hace posible, y lo que hoy nos parece complicado de
implementar --por ejemplo un *refactor*-- se podría implementar como
un `UPDATE` a un campo de una tabla. Un proyecto que apunta a esto
es: [Lamdu](http://peaker.github.io/lamdu/).

Existe todo un mundo detrás de la manipulación del texto en la
programación. Somos artesanos del texto. Y con esto no me refiero a
ser escritores. Sino que me refiero a la cantidad de tiempo invertido
en cosas inútiles que no afectan al código. Ejemplos: espacios en
blanco, tamaño de los tabs, cantidad de columnas en la pantalla,
nuevas líneas y enters (CRLF vs CR vs LF), nivel de sangría, etc.  Y
esto lo debemos acordar inclusive en equipos que muchas veces deben
luchar con las preferencias personales de cada integrante.

¿Por qué cuando programamos no nos podemos concentrar únicamente en la
lógica del programa? ¿Por qué debemos lidear con todos estos problemas
sobre caracteres que *no vemos*? Y el problema no es sólo en los
editores de texto, se extiende a programas controladores de versiones
(ej: git), páginas para revisar código --que deben mostrar estos
caracteres--, herramientas para formatear el código, herramientas para
buscar código (find/grep), etc.

Por ahora veo lejos la posibilidad de reemplazar los editores de
texto. Y a pesar de todos los problemas anteriores, la entrada y
navegación de caracteres es más ágil que cualquier otra cosa.
Igualmente así, la edición, navegación, presentación, comparación, y
control de versiones de árboles AST abre todo un nuevo mundo de
opciones que hoy en día se nos escapa por estar preocupados en si un
tab debe tener un ancho de 4 u 8 espacios.

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
