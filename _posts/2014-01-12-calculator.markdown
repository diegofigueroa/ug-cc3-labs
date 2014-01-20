---
layout: post
title:  "Laboratorio #1"
subtitle:  "Calculadora"
date:   2014-01-16 21:28:27
categories: labs
published: true
due_date: 2014-01-22
excerpt: Introducción al lenguaje C.
tags: c calculator
---

## Objetivos

Esta práctica es para familizarizarse con el lenguaje C, porque les va a ser muy útil para el resto del curso.  
Los objetivos para este laboratorio son:

- Que tomen práctica programando en C.
- Apliquen los temas vistos en clase sobre C.
- Que practiquen un poco y se diviertan con C ;)

---

## Descripción

Iniciaremos nuestro laboratorio de CC3 familiarizándonos con el lenguage de programación ANSI C.  
Después de haber estado programando un año en dos lenguajes distintos, es el momento de probar sus habilidades para adaptarse rápidamente a un nuevo lenguaje.  
Usted ya sabe programar, solo necesita estudiar la sintaxis del lenguaje nuevo y realizar algunos ejercicios para adaptarse.  
Contará con el apoyo de sus auxiliares, y por supuesto, Google.

---
## Ambiente de trabajo

Estaremos trabajando con ANSI C, sugerimos utilizar el compilador GCC en Linux/OS X y Dev-C en Windows.

### GCC
Para compilar un programa con el estándar ANSI C usando `gcc`, debe escribir el siguiente comando:

{% highlight bash %}
$ gcc -ansi archivo.c
{% endhighlight %}

El compilador verificará el código para luego generar un archivo ejecutable llamado `a.out`

Para ejecutar el archivo generado escribimos el nombre del ejecutable:

{% highlight bash %}
$ ./a.out
{% endhighlight %}

Si desea que su archivo ejecutable tenga un nombre en especial compilamos de la siguiente manera:

{% highlight bash %}
$ gcc -ansi archivo.c -o nuevonombre
{% endhighlight %}

En este caso lo ejecutamos con:

{% highlight bash %}
$ ./nuevonombre
{% endhighlight %}

### DEV C++

El instalador de dev-c esta en el GES bajo material de apoyo, pueden descargarlo e instalarlo; luego hacer un nuevo archivo haciendo click en file->new->source file o utilizando el shortcut `ctrl+n`.

Para compilar pueden hacerlo utilziando el shortcut `ctrl+F9` Como nos interesa que sea ANSI C, entonces debemos agregar esta restriccion dirigiendonos al menú tools->compiler options y escribiendo -ansi en la caja de texto que se encuentra bajo el titulo "Add these commands to the linker command line" y colocando un cheque al lado izquierdo de este título.

Para ejecutar utilizamos el shortcut `ctrl+F10` o para realizar ambas cosas a la vez (compilar & ejecutar) utilizamos `F9`.

--
## Ejercicio #1

Deberá construir una calculadora en ANSI C, con soporte para las siguientes operaciones

- Suma
- Resta
- Multiplicación
- División
- Potenica (elevar 'm' a la 'n')
- Requisitos adicionales

Recibirá los parámetros por la línea de comandos de la forma `num op num`, por ejemplo:

{% highlight bash %}
$ ./lab1 5 + 2
{% endhighlight %}

La firma de la función `main` es:


{% highlight c %}
int main(int argc, char** argv);
{% endhighlight %}

Donde `argc` es la cantidad de argumentos en la línea de comandos y `argv` un arreglo en el que cada posición es un argumento. El primer argumento es el nombre del programa, por ejemplo:

{% highlight c %}
printf("%s\n",argv[0]); /* imprime el nombre del programa */
{% endhighlight %}

Cada argumento recibido es una cadena de carácteres, pero C no tiene un tipo de dato `String`, entonces lo representa como un arreglo de caracteres, si la llamada al programa es:

{% highlight bash %}
$ ./lab1 12 * 3
{% endhighlight %}

entonces es posible hacer:

{% highlight c %}
printf("%c\n",argv[1][0]); /* imprime 1 */
{% endhighlight %}

pero:

{% highlight c %}
printf("%i\n",argv[1][0]); /* imprime 49 */
{% endhighlight %}

esto es debido al ASCII del caracter, para nuestros fines, convertiremos a un entero usando la función atoi:

{% highlight c %}
printf("%i\n",atoi(argv[1])); /* imprime 12 */
{% endhighlight %}

Su laboratorio devolverá como respuesta el resultado de la operación o un error cuando aplique:

- Si la cantidad de argumentos de la línea de comandos no es la adecuada debe mostrar un error y no realizar la operación.
- Si en la división el denominador (segundo parámetro) es cero debe mostrar un mensaje de error y no realizar la operación.
- Para el cálculo de potencia, debe realizar una función llamada 'elevar' que reciba los argumentos 'm' y 'n' y devuelva el resultado de m a la n. Es muy importante que respete este nombre porque lo utilizaremos al calificar:

{% highlight c %}
int elevar(int m, int n)
{% endhighlight %}

Es muy importante que utilice solo funciones de las librerias ANSI C, en el GES puede encontrar un reference card indicando cuales son estas librerias. Quien utilice funciones ajenas a ANSI C será sancionado con puntos menos.

#### Ejemplos de ejecuciones de su programa:

{% highlight c %}
$ ./lab1 4 * 3
$ 12

$ ./lab1 4 *
$ Error

$ ./lab1 14 / 0
$ Error
{% endhighlight %}

--
## Preguntas frecuentes

- Q. ¿Cómo escribo algo a pantalla?
- A. `printf("hola mundo!");`

- Q. ¿Cómo escribo un número a pantalla?
- A. `printf("Este es un número uno: %i",1);`

- Q. ¿Cómo leo un número del teclado y lo guardo en una variable?
- A. `int opc; scanf("%i", &opc);` Nótese que es necesario colocar un `&` antes del nombre de la variable. Por el momento acepten esto como dogma y cuando veamos punteros entderán la razón :)

- Q. ¿Debo incluir alguna libreria?
- A. sí, debe incluir al inicio de su programa la directiva include de la siguiente forma `#include <stdio.h>`

--
## Entrega

La entrega se realizará a través del `GES` antes de las **23:55:00** del día **Miércoles 22 de enero 2014**, debe enviar un archivo llamado `carnet.c` conteniendo su programa.  
  
No envíe archivos `.zip`, `.rar` , `.7z` o similares. Si lo hace, su respuesta **no** será tomada en cuenta.

--