---
layout: post
title: "He creado un bot de Telegram para votar publicaciones de Creary"
categories:
- criptomonedas
- Tecnología
tags: 
- Creary
- Telegram Bot
- API de Telegram
- Creando un bot de Telegram
- NodeJS
image: /assets/images/images_posts/botTelegram.jpg
lang: "es-MX"
comments: true
---

En las últimas semanas he tenido en mente dos cosas principalmente, mejorar mis conocimientos de Javascript y usar NodeJS (Javascript desde el lado del servidor) y saber como crear un bot para Telegram. Asi que despues de andar viendo la [API que tiene Telegram para sus bots me puse a experimentar un poco.](https://core.telegram.org/bots/api){:target="_blank"}

Como resultado he creado un bot, que, quien lo use pueda compartir su post de [Creary](https://shadowmyst.net/que-es-creary/){:target="_blank"} y el bot automáticamente votará por la publicación usando mi cuenta secundaria [@escuadron201](https://creary.net/@escuadron201){:target="_blank"}, de esta forma puedo darle nuevamente actividad a esta cuenta y podría emplearse bien su poder de voto.

![](/assets/images/voto.jpg){: .image .image-centered .is-512}

Como pueden ver su uso es sencillo, de igual forma si el bot lo meten a un grupo (y le dan permisos de administrador) al detectar un enlace de un post de Creary este votará automáticamente por el. Puedes encontrar el bot como @escuadron201_bot en Telegram o [directamente desde este link](https://t.me/escuadron201_bot){:target="_blank"}

Entre las cosas que quiero agregar, es que también reconozca enlaces de Hive y vote por las publicaciones, aunque creo que los enlaces que buscaré que reconozca sean los de [peakd](https://peakd.com){:target="_blank"}. De igual forma tengo que agregar en que si el poder de voto baja del 80% los votos sean detenidos o reducir la fuerza de voto, ya que, actualmente podrían acabarse mi poder de voto sin problemas.

Aún no se cual sera el alcance de este bot, tengo muchas ideas locas que debo lograr aterrizar en código como el poder intercambiar tokens CREA con los de HIVE y viceversa, ver qué otras funcionalidades relacionadas a la blockchain se puedan agregar, etc. Por el momento me estoy divirtiendo al programar esto (y mejorando como programador que me sentía estancado), pero también acepto ideas externas, así que, si tienes en mente alguna funcionalidad que te gustaria que agregara al bot, no dudes en comentarlo.

