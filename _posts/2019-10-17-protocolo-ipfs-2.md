---
layout: post
title: "IPFS Parte 2 - IPNS"
categories:
- Tecnología
tags: 
- IPFS
- protocolo IPFS
- P2P
- Torrent
image: /assets/images/images_posts/ipfs-logo.png
lang: "es-MX"
comments: true
---

[La primera parte]({% post_url 2019-10-12-protocolo-ipfs %}) sirvió como introducción para hablar sobre IPFS y conocer un poco del protocolo, ahora es momento de alojar nuestra página web y para ello vamos a ayudarnos de IPNS, que nos funcionaria como el propio DNS de IPFS.

Hay que aclarar que las web’s recomendadas para IPFS son las web estáticas y lo más dinámico que pueden tener es el uso extenso de Javascript para conectarse a API’s, para poder obtener y actualizar su información. Esta es una de las razones por las que para este blog decidí ya no usar IPFS, pues mi contenido aunque parece estático, realmente va cambiando al generar un nuevo post. Pues si la web prácticamente no tiene nada de Javascript, a excepción de una o dos cositas y el JS de Google Analytics y Google Adsense

## Agregando nuestra web estática en IPFS
{: .subtitle .has-text-centered .is-size-2 has-text-weight-bold}

Algo que no mencione en el primer artículo, es que podemos agregar a IPFS toda una carpeta completa y es la forma en que podemos agregar todo un sitio con su CSS, JS, imágenes y más archivos html dentro de IPFS.

Supongamos que quiero almacenar este sitio creado con Jekyll, para hacerlo iré a la carpeta donde se creó todo el sitio web y escribiría el siguiente comando desde la terminal

~~~
ipfs add -r _site
~~~

```_site``` Es donde esta alojado todo el contenido de shadowmyst.net una vez se ha generado con Jekyll y hay que prestar atención al hash final de la carpeta una vez que se agregó todo nuestro contenido a IPFS

![Agregando una carpeta a IPFS](/assets/images/images_posts/carpeta-ipfs.png){: .image}

El hash de nuestra carpeta es: “QmUVbwmm5vBx1cR9RCAMTUy4brs6WRGLeirMkiYfsxaMq1” pero ojo, este es el hash de la carpeta hasta donde se creó el primer post sobre IPFS, si quisiera agregar el post que estoy escribiendo ahorita y lo subiera a IPFS tengan por seguro que el hash será completamente diferente.

Entonces ¿que pasa si estamos actualizando contenido constantemente?. Si quisieramos llevar a nuestra web al mundo y querer que las personas comunes nos visiten, aparte del chorizote de hash para acceder al [gateway de ipfs](https://ipfs.io/ipfs/QmUVbwmm5vBx1cR9RCAMTUy4brs6WRGLeirMkiYfsxaMq1){:target='_blank'}, tendriamos que compartir a todos la url para cada hash que se cree cuando hagamos cambios en nuestro sitio. Pero para solucionar eso tenemos IPNS.

IPNS es lo más parecido que tenemos a un DNS, usa nuestro ID de nuestro nodo IPFS (igual puedes crear otras especies de ID, pero no lo abordaré aquí, si estas interesado puedes dejar un comentario), puedes saber tu ID si en la terminal colocas ipfs id.

Para publicar nuestra web usando IPNS es simple, usando el comando “ipns name publish HASH”, donde HASH es el de la carpeta de nuestro sitio”

~~~
ipfs name publish QmUVbwmm5vBx1cR9RCAMTUy4brs6WRGLeirMkiYfsxaMq1
~~~

Así podemos acceder a nuestro sitio web directamente usando nuestro solo que tendriamos que cambiar el /ipfs/ por /ipns/ en lo que seria nuestro url ```http://localhost:8080/ipns/HASH_ID``` (para el caso directamente verlo desde nuestro nodo o ```https://ipfs.io/ipns/HASH_ID``` (si lo queremos ver desde el gateway de la pagina web de ipfs).

Ahora ya no tendrás que preocuparte por cada vez que hagas una actualización de tu sitio, porque cada vez que apliques el comando anterior con el nuevo hash de tu carpeta, el usuario podra acceder a tu sitio web sin problemas.

Sin embargo, sigue siendo una dirección web nada amigable, para ello podemos usar DNSLINK, el cual nos ayuda a que un dominio, apunte a nuestro hash IPNS.

Para ello añadimos un campo TXT en los DNS de nuestro dominio. El contenido es el siguiente: ```dnslink=/ipns/HASH```

Pero también tenemos que agregar un registro A de nuestro dominio, para que apunte a un gateway ipfs, lo más conocidos es el que ya hemos usado en ipfs.io, asi que emplearemos ese, pero necesitamos averiguar la IP, para no complicarse la vida, la ip de el gateway de ipfs.io es 209.94.90.1.

- Registro A:
  ![Cambiar Registro A](/assets/images/images_posts/registroA-ipfs.png){: .image}

- Registro TXT:
  ![Cambiar Registro A](/assets/images/images_posts/registroTXT.png){: .image}

Para ver el resultado de este ejemplo, pueden visitar [este link](http://conservacionmaicesnativomexicanos.com/){:target="_blank"}, un dominio que tengo bajo mi control ya que un cliente no me pagó por el desarrollo de su web.

Y listo puedes tener alojado tu sitio web estático, sin embargo la razón principal por la que ya no escogí usar IPFS, es porque sigue siendo un protocolo lento, si no hay más nodos IPFS que guarden una copia de tu sitio, entonces, un sitio web puede tardar hasta un minuto en cargarse dependiendo cuantos nodos estén conectados a ese gateway, tal vez si mi web fuera algo estático, lo dejaría sobre ipfs, pero al ser un sitio que cambia de hash constantemente en cada post, esas copias que se vayan guardando en otros nodos quedan de alguna forma inservibles.

Pero IPFS es un protocolo que pienso usar en otros proyectos descentralizados, por ejemplo la blockchain de Creary del que ya tengo en mente varias dapps que pienso desarrollar.