Introducción
============

Objetivos
---------

Los objetivos del presente trabajo son los siguientes:

-   Familiarizarse con el sistema de entregas SERCOM

-   Preparación del ambiente de trabajo propio

-   Nivelar conocimientos básicos en C

-   Preparación de informe técnico

En las siguientes secciones se vera plasmado el cumplimiento de los
objetivos.

Secciones
---------

El presente trabajo práctico está dividido en secciones que las podemos
dividir en dos grandes categorías. La primera es la introducción en
donde se enumeran los objetivos y se informa como se estructurara el
informe.La segunda son los pasos en los que se dividió el proyecto. Allí
se hará un análisis exhaustivo de cada paso.

Paso 0: Entorno de Trabajo
==========================

Entorno de trabajo local
------------------------

Si bien SERCOM es capaz de compilar y someter a prueba las entregas,
usarlo como entorno de trabajo remoto es lento e ineficiente. Por eso es
importante configurar un entorno de trabajo local.

### Sistema operativo

![\[fig:class01\]Sistema operativo
utilizado](Imagenes/Sistema_operativo.png)

### Herramientas

![\[fig:class01\]Herramientas
utilizadas](Imagenes/Herramientas.png)

Hola Mundo
----------

Se compilo y ejecuto una aplicación simple ISO C que imprimio por
pantalla el mensaje “Hola Mundo” y finalizo retornando 0 (cero).

![\[fig:class01\]Compilación y ejecución sin
valgrind](Imagenes/Ejecutar_Hola_Mundo.png)

![\[fig:class01\]Ejecución con
valgrind](Imagenes/Valgrind_Hola_Mundo.png)

Repaso de C
-----------

Los temas a repasar en esta sección son los siguientes:

-   Funciones para el manejo de archivos

-   Manejo de memoria dinámica

-   Punteros y aritmética de punteros

-   Entrada y salida estándar

-   Proceso de compilación

-   Uso de operadores a nivel de bits

-   Concepto y uso del debugger

### Funciones para el manejo de archivos

La estructura de datos FILE es definida en el fichero de cabecera
stdio.h para el manejo de ficheros. Siempre usaremos punteros a estas
estructuras.La sintaxis de sus funciones principales es:

-   fopen: FILE \*fopen(char \*nombre, char \*modo);

-   fclose: int fclose(FILE \*fichero);

### Manejo de memoria dinámica

-   C y C++ son lenguajes de bajo nivel para que el programador pueda
    tener un control absoluto de dónde y cómo se ejecuta el código.

### Punteros y aritmética de punteros

-   El tamaño de un puntero no depende de a que tipo apunta; todos los
    punteros ocupan el mismo tamaño (que depende de la arquitectura).

### Entrada y salida estándar

Las funciones estándar de entrada/salida se definen el el fichero de
cabeceras stdio.h.Las funciones principales son:

-   printf: escritura con formato (print-format) int printf(const char
    \*fmt, ...);

-   scanf: lectura con formato (scan-format) int scanf(const char \*fmt,
    ...);

### Proceso de compilación

La compilación es un proceso de conversión del código fuente en código
objeto. Se realiza con la ayuda del compilador. El compilador verifica
el código fuente en busca de errores sintácticos o estructurales, y si
el código fuente está libre de errores, genera el código objeto. El
proceso de compilación c convierte el código fuente tomado como entrada
en el código objeto o código máquina. El proceso de compilación se puede
dividir en cuatro pasos, es decir, preprocesamiento, compilación,
ensamblaje y vinculación(linker).El preprocesador toma el código fuente
como entrada y elimina todos los comentarios del código fuente. El
preprocesador toma la directiva del preprocesador y la interpreta. Por
ejemplo, si &lt;stdio.h&gt;, la directiva está disponible en el
programa, entonces el preprocesador interpreta la directiva y reemplaza
esta directiva con el contenido del archivo ’stdio.h’.

### Uso de operadores a nivel de bits

Los operadores bitwise se pueden usar para realizar operaciones a nivel
de bit en variables.Los operadores bitwise admitidos en C son los
siguientes:

-   **Y** en el bit y

-   **|** bitwise inclusive O

-   **\^** OR exclusivo a nivel de bit (XOR)

-   ** ** bitwise no (complemento de uno)

-   **&lt;&lt;** desplazamiento lógico a la izquierda

-   **&gt;&gt;** cambio lógico a la derecha

### Concepto y uso del debugger

El debugger es la herramienta principal para ver qué pasa en un
programa. En este trabajo utilizaremos gdb.La forma de iniciarlo es “gdb
executable”. El “executable” será conveniente que tenga su “debug info”,
esto es, la información que el compilador le adosa para decirle al
debugger qué líneas de código fuente corresponden a cuáles instrucciones
de código máquina. El GCC agrega esta información sólo si se le pasa la
opción -g en el momento de compilar.

¿Para qué sirve ​ Valgrind​ ? ¿Cuáles son sus opciones más comunes?
-------------------------------------------------------------------

Valgrind es un marco de instrumentación para construir herramientas de
análisis dinámico. Viene con un conjunto de herramientas, cada una de
las cuales realiza algún tipo de depuración, creación de perfiles o
tareas similares que lo ayudan a mejorar sus programas.

Las herramientas que se suministran como estándar son:

-   **Memcheck** es un detector de errores de memoria. Le ayuda a hacer
    que sus programas, particularmente los escritos en C y C ++, sean
    más correctos.

-   **Cachegrind** es un generador de perfiles de predicción de
    ramificación y caché. Le ayuda a hacer que sus programas se ejecuten
    más rápido.

-   **Callgrind** es un generador de perfiles de caché que genera
    gráficos de llamadas. Tiene cierta superposición con Cachegrind,
    pero también recopila información que Cachegrind no tiene.

-   **Helgrind** es un detector de errores de hilo. Le ayuda a hacer que
    sus programas multiproceso sean más correctos.

-   **DRD** también es un detector de errores de hilo. Es similar a
    Helgrind, pero utiliza diferentes técnicas de análisis y, por lo
    tanto, puede encontrar diferentes problemas.

-   **Massif** es un perfilador de montones. Le ayuda a hacer que sus
    programas usen menos memoria.

-   **DHAT** es un tipo diferente de perfilador de montón. Le ayuda a
    comprender los problemas de vida útil de los bloques, la utilización
    de bloques y las ineficiencias de diseño.

-   **SGcheck** es una herramienta experimental que puede detectar
    desbordamientos de pila y matrices globales. Su funcionalidad es
    complementaria a la de Memcheck: SGcheck encuentra problemas que
    Memcheck no puede, y viceversa.

-   **BBV** es un generador experimental de vectores de bloques básicos
    SimPoint. Es útil para las personas que realizan investigación y
    desarrollo de arquitectura de computadoras.

¿Qué representa sizeof()? ¿Cuál sería el valor de salida de sizeof(char) y sizeof(int)?
---------------------------------------------------------------------------------------

El operador sizeof es un operador unario en tiempo de compilación y se
usa para calcular el tamaño de su operando. Devuelve el tamaño de una
variable. Se puede aplicar a cualquier tipo de datos, tipo flotante,
variables de tipo puntero.Cuando sizeof () se usa con los tipos de
datos, simplemente devuelve la cantidad de memoria asignada a ese tipo
de datos. El valor de salida de sizeof(char) no depende del compilador
en el que se este trabajando, va ser simpre 1 byte, mientras que para
sizeof(int) podra ser 2 bytes o 4 bytes dependiendo de si se esta
trabajando con un compilador de 16 bits, 32 bits o 64 bits.

¿El sizeof() de una struct de C es igual a la suma del sizeof() de cada uno sus elementos?
------------------------------------------------------------------------------------------

El sizeof() de una struct de C no es igual a la suma del sizeof() de
cada uno sus elementos. Para demostrar esto realice un contra ejemplo
donde genero un programa que imprime por pantalla el sizeof() de un
struct que contiene un char, un int, un float y un double.

![\[fig:class01\]Sizeof() strcut vs suma de sizeof() de cada
elemento](Imagenes/Sizeof.png)

El resultado es distinto a la suma de cada uno de los sizeof(). Esto se
debe a que el compilador agrega padding con el objetivo de ganar
velocidad al momento de acceder a los datos del struct a cambio de
perder memoria. En caso de necesitar esta memoria hay opciones de
compilación que evita que el compilador realice padding, una de ellas es
’package’.

STDIN, STDOUT, STDERR
---------------------

Las tres secuencias estándar que se establecen cuando se ejecuta un
comando de Linux son stdin, stdout y stederr. stdin es el flujo de
entrada estándar. La salida de texto del comando al shell se entrega a
través de la secuencia stdout (salida estándar). Los mensajes de error
del comando se envían a través de la secuencia stderr (error
estándar).Las secuencias stdin, stdout y stderr se pueden redireccionar
mediante los caracteres ’&gt;’ y ’&lt;’. A continuación mostraremos un
ejemplo donde la salida del programa es mostrada en un txt utilizando el
caracter ’&gt;’. El comando pipe ’|’ es utilizado para conectar el
stdout de un programa con el stdin de otro. Se utiliza de la forma:
sentencia|sentencia2

![\[fig:class01\]Redireccionamiento
stdout](Imagenes/Redireccionamiento.png)

Paso 1: SERCOM - Errores de generación y normas de programación
===============================================================

Entrega rechazada
-----------------

La entrega del primer paso fallo. Podemos visualizar en rojo las tareas
fallidas y descargar los archivos de salida sterr donde podremos
observar con mas detalle los errores obtenidos.

![\[fig:class01\]Entrega rechazada
SERCOM](Imagenes/Entrega_rechazada_paso1.png)

Errores de normas de programación
---------------------------------

A continuación se analizarán los errores de normas de programación
cometidos en esta entrega. Los números que están entre corchetes al
final de cada error representan que tan grave es el error. Estos van del
1 al 5 siendo esta última la puntuación máxima.

![\[fig:class01\]Errores de normas de
programación](Imagenes/Errores_normas_SERCOM_paso1.png)

En el archivo `paso1_wordscounter`.c encontramos:

-   `paso1_wordscounter`.c:27: Missing space before ( in while(
    \[whitespace/parens\] \[5\] : Falta un espacio entre el while y el
    partentesis de la condición en la linea 27.

-   ./`paso1_wordscounter`.c:41: Mismatching spaces inside () in if
    \[whitespace/parens\] \[5\] : Difiere la cantidad de espacios de
    ambos lados del if de la linea 41.

-   ./`paso1_wordscounter`.c:41: Should have zero or one spaces inside (
    and ) in if \[whitespace/parens\] \[5\] : Hay más de un espacio
    dentro de los parentesis de la linea 41.

-   ./`paso1_wordscounter`.c:47: An else should appear on the same line
    as the preceding \[whitespace/newline\] \[4\] : Hay un salto de
    linea entre el cierre de llaves y el else de la linea 47. Deben
    estar en la misma linea.

-   ./`paso1_wordscounter`.c:47: If an else has a brace on one side, it
    should have it on both \[readability/braces\] \[5\] : Esta solamente
    la apertura de llaves del else de la linea 47. En dicha linea
    también debería estar la llave de cierre del if.

-   ./`paso1_wordscounter`.c:48: Missing space before ( in if(
    \[whitespace/parens\] \[5\] : Falta un espacio entre el if y la
    apertura de parentesis de la linea 48.

-   ./`paso1_wordscounter`.c:53: Extra space before last semicolon. If
    this should be an empty statement, use instead.
    \[whitespace/semicolon\] \[5\] : Hay un espacio extra antes del
    punto y coma de la linea 53.

En el archivo `paso1_wordscounter`.h encontramos:

-   ./`paso1_wordscounter`.h:5: Lines should be &lt;= 80 characters long
    \[whitespace/`(`line\_length)\] \[2\] : La linea 5 supero los 80
    caracteres. De todas maneras es un error leve porque tiene
    puntuación de 2.

En el archivo `paso1_main`.c encontramos:

-   ./`paso1_main`.c:12: Almost always, snprintf is better than strcpy
    \[runtime/printf\] \[4\] : Recomienda utilizar snprintf en vez de
    strcpy en la linea 12.

-   ./`paso1_main`.c:15: An else should appear on the same line as the
    preceding \[whitespace/newline\] \[4\] : Hay un salto de linea entre
    el cierre de llaves y el else de la linea 15. Deben estar en la
    misma linea.

-   ./`paso1_main`.c:15: If an else has a brace on one side, it should
    have it on both \[readability/braces\] \[5\] : Esta solamente la
    apertura de llaves del else de la linea 15. En dicha linea también
    debería estar la llave de cierre del if.

Errores de generación
---------------------

A continuación se analizarán los errores que impidieron generar el
ejecutable de esta entrega. Los números que están entre corchetes al
final de cada error representan que tan grave es el error. Estos van del
1 al 5 siendo esta última la puntuación máxima.

![\[fig:class01\]Errores de generación de
ejecutable](Imagenes/Errores_de_generacion_SERCOM_paso1.png)

Los errores que encontramos son los siguientes:

-   ./`paso1_main`.c:22:9: error: unknown type name ’`wordscounter_t`’
    `wordscounter_t` counter;

-   ./`paso1_main`.c:23:9: error: implicit declaration of function
    ’`wordscounter_create`’ \[-Wimplicit-function-declaration\]
    `wordscounter_create`(&counter);

-   ./`paso1_main`.c:24:9: error: implicit declaration of function
    ’`wordscounter_process`’ \[-Wimplicit-function-declaration\]
    `wordscounter_process`(&counter, input);

-   ./`paso1_main`.c:25:24: error: implicit declaration of function
    ’`wordscounter_get_words`’ \[-Wimplicit-function-declaration\]
    `(`size\_t) words = `wordscounter_get_words`(&counter);

-   ./`paso1_main`.c:27:9: error: implicit declaration of function
    ’`wordscounter_destroy`’ \[-Wimplicit-function-declaration\]
    `wordscounter_destroy`(&counter);

Todos se encuentran en `paso1_main`.c y refieren al mismo problema. Se
esta utilizando una libreria que no fue incluida, la misma es
”`paso1_wordscounter`.h. Estos errores se producen en la etapa de
compilación, previo a la etapa de linkeo.

Warnings
--------

No se reporto ningun warning porque en el make se esta utilizando el
flag werror. Este flag hace que todos los warning sean considerados como
errores.

Paso 2: SERCOM - Errores de generación 2
========================================

Cambios realizados respecto de la entrega anterior
--------------------------------------------------

En esta entrega se incluyo al main la librería ”`paso2_wordscounter`.h”,
la cual era necesaria para poder utilizar sus declaraciones.Además
corrigieron todos los errores de normas de programación que se habían
cometido en la entrega anterior. Entre ellos se cambio strcpy por memcpy
donde strcpy solo copiaba cadenas de texto mientras que memcpy copia
bytes sin importar su contenido.

![\[fig:class01\]Cambios realizados entre el paso1 y el
paso2](Imagenes/Cambios_paso1_paso2.png)

Entrega en SERCOM
-----------------

En esta entrega no hubo errores de normas de programación pero de todas
formas no resulto exitosa.

![\[fig:class01\]Entrega rechazada
SERCOM](Imagenes/Entrega_rechazada_paso2.png)

![\[fig:class01\]Entrega sin errores de normas de
programación](Imagenes/Errores_de_normas_de_programacion_paso2.png)

Errores de generación
---------------------

A continuación se analizarán los errores que impidieron generar el
ejecutable de esta entrega. Los números que están entre corchetes al
final de cada error representan que tan grave es el error. Estos van del
1 al 5 siendo esta última la puntuación máxima.

![\[fig:class01\]Errores de generación de
ejecutable](Imagenes/Errores_de_generacion_SERCOM_paso2.png)

Los siguientes errores refieren al mismo problema:

-   ./`paso2_wordscounter`.h:7:5: error: unknown type name ’`(`size\_t)’
    `(`size\_t) words;

-   ./`paso2_wordscounter`.h:20:1: error: unknown type name
    ’`(`size\_t)’ `(`size\_t) `wordscounter_get_words`(`wordscounter_t`
    \*self);

-   ./`paso2_wordscounter`.h:25:49: error: unknown type name ’FILE’ void
    `wordscounter_process`(`wordscounter_t` \*self, FILE \*text\_file);

Este es que se esta utilizando una librería que no fue incluida, la
misma es “stdio.h”.Los siguientes errores son consecuencias del error
anterior:

-   ./`paso2_wordscounter`.c:17:8: error: conflicting types for
    ’`wordscounter_get_words`’ `(`size\_t)
    `wordscounter_get_words`(`wordscounter_t` \*self)

-   ./`paso2_wordscounter`.c:20:8: note: previous declaration of
    ’`wordscounter_get_words`’ was here `(`size\_t)
    `wordscounter_get_words`(`wordscounter_t` \*self);

Estos se deben a que en el archivo `paso2_wordscounter`.c esta incluida
la librería “stdio.h” pero en el archivo `paso2_wordscounter`.h no lo
esta. Entonces no sabe que tipo dato devuelve la función en su
declaración pero si en su implementación. Al no estar seguro de que
coincidan ambos datos el compilador devuelve este error.Por último:

-   ./`paso2_wordscounter`.c:30:25: error: implicit declaration of
    function ’malloc’ \[-Wimplicit-function-declaration\] char\*
    `delim_words` = malloc(7 \* sizeof(char));

-   ./`paso2_wordscounter`.c:30:25: error: incompatible implicit
    declaration of built-in function ’malloc’ \[-Werror\]

-   ./`paso2_wordscounter`.c: 30:25: note: include ’&lt;stdlib.h&gt;’ or
    provide a declaration of ’malloc’

Acá se comete un error equivalente al anterior. Estamos utilizando la
función “malloc” de la librería “stdlib.h” sin incluir esta última. En
este caso el compilador nos esta haciendo notar este error diciendonos
que incluyamos dicha librería o declaremos la función.

Los errores de “unknown type name” e “implicit declaration of function”
son previos a la etapa de compilación. El error “conflicting types”
ocurre dentro de la etapa de compilación.

Paso 3: SERCOM - Errores de generación 3
========================================

Cambios realizados respecto de la entrega anterior
--------------------------------------------------

En esta entrega se incluyo la librería ”stdlib.h” la cual era necesaria
para poder utilizar la función “malloc”.

![\[fig:class01\]Cambios realizados entre el paso2 y el
paso3](Imagenes/Cambios_paso2_paso3.png)

Entrega en SERCOM
-----------------

Al igual que la entrega anterior, esta no tuvo errores de normas de
programación pero de todas formas no resulto exitosa.

![\[fig:class01\]Entrega rechazada
SERCOM](Imagenes/Entrega_rechazada_paso3.png)

![\[fig:class01\]Entrega sin errores de normas de
programación](Imagenes/Errores_de_normas_de_programacion_paso3.png)

Errores de generación
---------------------

A continuación se analizarán los errores que impidieron generar el
ejecutable de esta entrega. Los números que están entre corchetes al
final de cada error representan que tan grave es el error. Estos van del
1 al 5 siendo esta última la puntuación máxima.

![\[fig:class01\]Errores de generación de
ejecutable](Imagenes/Errores_de_generacion_SERCOM_paso3.png)

El error obtenido se debe a que hay una referencia a ’wordscounter
destroy’ dentro del main para la cual no se encontró definición en
ninguno de los archivos objeto o librerías incluidas. Este error ocurre
en la etapa de linkeo ya que se busca la definición en archivos externos
al main.

Paso 4: SERCOM - Memory Leaks y Buffer Overflows
================================================

Cambios realizados respecto de la entrega anterior
--------------------------------------------------

El principal cambio realizado en esta entrega fue la incorporación de la
definición de la función ’`wordscounter_ destroy`(`wordscounter_t`
\*self)’. La ausencia de esta definición fue la que impidió la
generación del ejecutable en el paso anterior.

![\[fig:class01\]Cambios realizados entre el paso3 y el
paso4](Imagenes/Cambios_paso3_paso4.png)

Entrega en SERCOM
-----------------

Al igual que las últimas entregas, esta no tuvo errores de normas de
programación. Al haber agregado la definición de la función que faltaba
tampoco tuvo errores de generación de ejecutable. De todas formas esta
tampoco resulto exitosa.

![\[fig:class01\]Entrega rechazada sin errores de normas ni de
generación
SERCOM](Imagenes/Entrega_rechazada_paso4.png)

![\[fig:class01\]Pruebas Realizadas
SERCOM](Imagenes/Entrega_rechazada_paso4_2.png)

Ejecución de Valgrind en TDA
----------------------------

La herramienta Memcheck de Valgrind es un detector de errores de
memoria. En este caso la misma nos informa que pedimos memoria para
alocar bytes y nunca la libe- ramos. Esto se puede observar en el HEAP
SUMMARY.

![\[fig:class01\]Valgrind TDA
SERCOM](Imagenes/Valgrind_TDA_paso4.png)

![\[fig:class01\]HEAP SUMMARY Valgrind TDA
SERCOM](Imagenes/Valgrind_TDA_Heap_Summary_paso4.png)

Si prestamos atención podemos observar que perdemos memoria debido a dos
errores. El primero se produce en el archivo `paso4_main`.c en la
función main donde se abre un archivo el cual nunca es cerrado. El
segundo se produce en `paso4_wordscounter`.c en la función
`wordscounter_next_state` donde se realiza un malloc el cual nunca es
liberado.

Ejecución de Valgrind en Long Filename
--------------------------------------

En esta prueba se ejecuta el contador de palabras con un archivo cuyo
nombre es muy largo. El error que se produce es un buffer overflow
dentro de la función main. Esto se debe a que la función memcpy tomo una
gran cantidad de datos y el buffer no la pudo soportar.

![\[fig:class01\]Valgrind Long Filename
SERCOM](Imagenes/Valgrind_Long_Filename_paso4.png)

En caso de utilizar la función strncpy en lugar de memcpy ocurriría el
mismo error ya que de igual manera se copiaría al buffer.

Segmentation fault y buffer overflow
------------------------------------

Se define como violación de acceso (violación segmentation fault en
Inglés) al intento fallido de acceso a información o a programas a los
que no se tiene autorización para ver o modificar. Este mensaje puede
ser causado por la configuración de software, por los programadores o
por fallo en el hardware, siendo los más comunes los 2 primeros.Un
desbordamiento de búfer (buffer overflow) es un error de software que se
produce cuando un programa no controla adecuadamente la cantidad de
datos que se copian sobre un área de memoria reservada a tal efecto
(buffer): Si dicha cantidad es superior a la capacidad preasignada, los
bytes sobrantes se almacenan en zonas de memoria adyacentes,
sobrescribiendo su contenido original, que probablemente pertenecían a
datos o código almacenados en memoria. Esto constituye un fallo de
programación.

Paso 5: SERCOM - Código de retorno y Salida estándar
====================================================

Cambios realizados respecto de la entrega anterior
--------------------------------------------------

Los cambios realizados con respecto a la entrega anterior son los
siguientes:

-   `delim_words` paso de ser un puntero a un string mutable a un
    puntero a un string inmutable (no ocupa memoria dinamica)

-   No se utiliza más memcpy en el main (pasa la prueba de Long
    Filename)

-   Se cierra el archivo de entrada del main (no se produce más perdida
    de memoria por dejarlo abierto)

![\[fig:class01\]Cambios realizados entre el paso4 y el
paso5](Imagenes/Cambios_paso4_paso5.png)

Entrega en SERCOM
-----------------

Al igual que las últimas entregas, esta no tuvo errores de normas de
programación. Con las últimas modificaciones logro pasar las pruebas de
‘TDA’, ‘C Language’, ‘STDIN’ y ‘Long Filename’ sin fallas de
Valgrind.Las pruebas ‘Invalid File’ y ‘Single Word’ no lograron correr
exitosamente.

![\[fig:class01\]Entrega rechazada sin errores de normas ni de
generación
SERCOM](Imagenes/Entrega_rechazada_paso5.png)

![\[fig:class01\]Pruebas Realizadas
SERCOM](Imagenes/Entrega_rechazada_paso_5_2.png)

Fallas en ‘Invalid File’ y ‘Single Word’
----------------------------------------

Por cada prueba que corra SERCOM que no resulte exitosa nos brinda una
observación para poder interpretar mejor el error. También nos permite
descargar los archivos de prueba para poder correrlos localmente en
nuestras maquinas y de esta forma solucionar el problema.En el caso de
’Invalid File’ la observación que nos brinda el sistema es “Se esperaba
terminar con un código de retorno 1 pero se obtuvo 255”.En el caso de
’Single Word’ la observación que nos brinda el sistema es “La salida
estándar no coincide con lo esperado (archivo ”`__stdout__.diff`“)”.
Como podemos observar en la siguiente figura el programa nos devuelve
que hay 0 palabras en el archivo cuando en verdad contiene una..

![\[fig:class01\]stdout
paso5](Imagenes/Stdout_paso5.png)

Esto se debe a que el archivo de prueba no tiene ninguno de los
caracteres separadores de palabra determinados en el programa.

Comando Hexadump
----------------

En la siguiente figura se puede observar que el ultimo carácter es un
64, en base hexadecimal. Si lo pasamos a decimal es un 100. Buscando
dicho valor en la tabla ASCII vemos que es una ’d’. Esta coincide con la
ultima letra de la palabra ’word’.

![\[fig:class01\]Hexadump
paso5](Imagenes/Hexdump_paso5.png)

Ejecución con GDB
-----------------

![\[fig:class01\]Inicio GDB con
tp](Imagenes/GDB_paso5-1.png)

Los comandos utilizados en GDB fueron los siguientes:

![\[fig:class01\]GDB info
functions](Imagenes/GDB_paso5-2.png)

info functions: Muestra la lista de funciones en el programa indicado.

![\[fig:class01\]GDB list
`wordscounter_next_state`](Imagenes/GDB_paso5-3.png)

list `wordscounter_next_state`: Imprime las lineas que están alrededor
de la función indicada.

![\[fig:class01\]GDB list](Imagenes/GDB_paso5-4.png)

list: Imprime las siguientes 10 lineas a partir de la ultima que se vio.

![\[fig:class01\]GDB: break
45](Imagenes/GDB_paso5-5.png)

break 45: Crea un punto de interrupción en una línea, dirección o
función especificada. En este caso la linea 45.

![\[fig:class01\]GDB: run
`input_single_word.txt`](Imagenes/GDB_paso5-6.png)

run `input_single_word.txt`: Empieza la ejecución de una nueva instancia
del programa bajo GDB.

![\[fig:class01\]GDB: quit](Imagenes/GDB_paso5-7.png)

quit: Finaliza la ejecución de GDB.

El debbuger no se detuvo en el breakpoint de la linea 45 porque no
ejecuto dicha linea.

Paso 6: SERCOM - Entrega exitosa
================================

Cambios realizados respecto de la entrega anterior
--------------------------------------------------

Los cambios realizados con respecto a la entrega anterior son los
siguientes:

-   Se definio a DELIM WORDS como una constante global

-   Se determino en la función `wordscounter_next_state` que si el
    próximo carácter encontrado es EOF y esta en una palabra el contador
    sume (así pasa la prueba Single Word)

![\[fig:class01\]Cambios realizados entre el paso5 y el
paso6](Imagenes/Cambios_paso5_paso6.png)

Entregas realizadas
-------------------

Las entregas realizadas hasta el momento son las siguientes:

![\[fig:class01\]Todas las entregas realizadas hasta el
paso6](Imagenes/Entregas_realizadas_hasta_paso6.png)

Prueba local Single Word
------------------------

![\[fig:class01\]Prueba local Single Word
paso6](Imagenes/Single_Word_local_paso6.png)
