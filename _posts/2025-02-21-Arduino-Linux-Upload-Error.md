---
layout: post
title: "Error al subir sketch de Arduino en Zorin OS"
date: 2025-02-21 10:00:00 +0000
categories: [blog, jekyll]
tags: [jekyll, tutorial]
author: "Edalmava"
---

Al intentar subir(upload) el sketch en la tarjeta Arduino UNO usando el IDE de Arduino 2.3.4 en
la distribución linux Zorin OS 17.2.  Me encontre con el siguiente error: **can't open device "/dev/ttyUSB0": Permission denied**

Este error ocurre porque el usuario no tiene permiso de acceso al puerto serial. Para solucionar se debe agregar el usuario al grupo **dialout** que es el propietario del archivo del dispositivo serial.  

Para hacer esto en el terminal, escribir lo siguiente:
~~~
sudo usermod -a -G dialout <username>
~~~

Se debe reiniciar la sesión para que se tomen los cambios

[Leer en la documentación](https://docs.arduino.cc/software/ide-v2/tutorials/getting-started/ide-v2-uploading-a-sketch/#please-read-only-linux-users)