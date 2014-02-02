---
layout: post
title:  "Laboratorio #7"
subtitle:  "Control de flujo en MIPS"
date:   2014-02-04 06:28:27
categories: labs
published: true
due_date: 2014-02-05
excerpt: Aprendiendo sobre control de flujo en MIPS
tags: mips flow-control
---

## Objetivos

- Poner en práctica conceptos básicos vistos sobre MIPS.
- Familiarizarse con el uso del simulador de MIPS MARS.
- Tomar práctica sobre control de flujo en MIPS.

---

## Ambiente de trabajo

Debe descargar del GES, en la sección de materil de apoyo, el simulador MARS (un .jar). Adicionalmente deberá tener
el runtime de Java instalado.

--

## Descripción

Para este laboratorio vamos a realizar un programa de MIPS conteniendo 2 funciones iterativas.
Para ayudarlo un poco le damos las funciones en lenguaje C:

{% highlight c %}
// suma secuencial

int sumaseq(int n) {
  int res = 0;
  for (int i = 1; i <= n; i++) {
    res = res + i;
  }
  return res;
}

// factorial

int factit(int n) {
  int res = 1;
  for (int i = n; i > 0; i--) {
    res = res * i;
  }
  return res;
}

{% endhighlight %}

--
## Entrega

La entrega se realizará a través del `GES` antes de las **23:55:00** del día **Miércoles 26 de febrero 2014**, debe enviar un archivo llamado `carnet.s` conteniendo su programa.  
  
No envíe archivos `.zip`, `.rar` , `.7z` o similares. Si lo hace, su respuesta **no** será tomada en cuenta.

-- 
