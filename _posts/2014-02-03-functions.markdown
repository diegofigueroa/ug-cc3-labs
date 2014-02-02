---
layout: post
title:  "Laboratorio #6"
subtitle:  "Funciones en MIPS"
date:   2014-02-03 06:28:27
categories: labs
published: true
due_date: 2014-02-05
excerpt: Escribiendo funciones en MIPS
tags: mips functions
---

## Objetivos

- Poner en práctica conceptos básicos vistos sobre MIPS.
- Familiarizarse con el uso del simulador de MIPS MARS.
- Tomar práctica escribiendo funciones en MIPS.

---

## Ambiente de trabajo

Debe descargar del GES, en la sección de materil de apoyo, el simulador MARS (un .jar). Adicionalmente deberá tener
el runtime de Java instalado.

--

## Descripción

Para este laboratorio vamos a realizar un programa de MIPS para solucionar el problema de las torres de hanoi, 
para ayudarlo un poco le damos el código de la función en C:

{% highlight c %}
void hanoi(int NumeroDeDiscos, int T_Origen, int T_Destino, int T_Alterna){
    if(NumeroDeDiscos == 1){
	  printf(" mueva el disco de la torre: "); printf("%i",T_Origen);
	  printf(" hacia la torre: "); printf("%i",T_Destino); printf("\n");
    }else{
	  hanoi(NumeroDeDiscos - 1, T_Origen, T_Alterna, T_Destino);
	  hanoi(1, T_Origen, T_Destino, T_Alterna);
	  hanoi(NumeroDeDiscos - 1, T_Alterna, T_Destino, T_Origen);
    }
}
{% endhighlight %}

--
## Entrega

La entrega se realizará a través del `GES` antes de las **23:55:00** del día **Miércoles 19 de febrero 2014**, debe enviar un archivo llamado `carnet.s` conteniendo su programa.  
  
No envíe archivos `.zip`, `.rar` , `.7z` o similares. Si lo hace, su respuesta **no** será tomada en cuenta.

-- 
