---
layout: post
title: "El Protocolo IPFS"
categories:
- Tecnología
tags: 
- IPFS
- protocolo IPFS
- P2P
- Torrent
cabecera: /assets/images/images_posts/ipfs-logo.png
comments: true
---
Durante el tiempo en que estuve actualizando la página web, una de mis primera intenciones alojarla usando el protocolo IPFS, sin embargo al final decidí alojarme en el servidor donde tengo alojado mi nodo de [Creary](% post_url 2019-08-26-que-es-creary %). Pero debo mencionar que IPFS es algo que vale la pena conocer, sobre todo si te gustan los sistemas P2P.


## ¿Qués es IPFS?
{: .subtitle .has-text-centered .is-size-3 has-text-weight-bold}

IPFS son las siglas en inglés de **“Sistema de Archivos Interplanetario”**, hay que reconocer que se rifaron con el nombre. IPFS es un protocolo y red P2P diseñado para poder almacenar compartir cualquier clase de archivos de forma distribuida entre los nodos que usan el protocolo como usuarios externos.

En un internet completamente centralizado siempre surgen alternativas que quieren ser libres que siempre buscarán la descentralización, entre esas cosas podemos encontrar, alternativas como Tor, i2p, Torrent, la tecnología blockchain (de las cuales son muy adepto), y ahora en este caso hablemos de IPFS, al que le podemos considerar torrent 2.0. Gracias a su facultad de poder compartir archivos a través de sus nodos y su facultad para poder almacenar páginas estáticas a las que podemos colocar un DNS para que no URL muy largas.

IPFS busca conectar todos los dispositivos informáticos en su protocolo, prácticamente como lo que conocemos como internet actual y de alguna forma busca reemplazar al ya viejo protocolo HTTP (que está cerca de llegar a su tercera versión), ya que tiene las ventajas de no poder recibir ataques DDoS, y su servicio de nombres IPNS que es compatible con los NS (Name Server) que nos servirá para poderle asignar dominios más tradicionales como este blog de dominio [shadowmyst.net](https://shadowmyst.net)


## ¿Como tener un nodo IPFS?
{: .subtitle .has-text-centered .is-size-3 has-text-weight-bold}

Realmente tenerlo e instalarlo es demasiado sencillo y está disponible tanto para Windows, Mac y Linux. Se encuentra implementada en el lenguaje de programación de GO, aunque existe una versión para Javascript, sigue siendo la más utilizada su versión de GO que puedes ([descargar desde aqui](https://dist.ipfs.io/#go-ipfs))

Despues de instalarlo lo iniciamos de la siguiente manera:
```
ipfs init
ipfs init --profile server //esta opcion en caso de que lo uses como centro de datos, ya reduce el tráfico interno
```
Al momento de aplicar esto se nos creara un hash RSA para el nodo que es clave para su funcionamiento ademas de nuestra ID que es lo que identifica nuestro nodo ante toda la red.

Para podernos comunicar con los demas nodos, necesitamos tener prendido el daemon y esto se hace de forma sencilla: ```ipfs daemon```. Con ello ya nos podremos comunicar
a través de la red, podremos agregar y compartir nuestros archivos al mundo. Por ejemplo guardare el logo de la pagina de la siguiente manera:
```
ipfs add 'logo shadow myst.jpg
```
Que dara como resultado un mensaje de la siguiente manera
```
added QmSRkkgJjfp2EisqBCtwijwVKPg98qV9a4CZ8yPEbZCH44 logo shadow myst.jpg
```

Si quieren acceder a este archivo desde su nodo ipfs pueden entrar directamente a [https://ipfs.io/ipfs/QmSRkkgJjfp2EisqBCtwijwVKPg98qV9a4CZ8yPEbZCH44](https://ipfs.io/ipfs/QmSRkkgJjfp2EisqBCtwijwVKPg98qV9a4CZ8yPEbZCH44) o desde su terminal agregarlo de igual forma con el comando add
```
ipfs add /ipfs/QmSRkkgJjfp2EisqBCtwijwVKPg98qV9a4CZ8yPEbZCH44
```
Pero lo que hace add es guardar una copia en cache de los archivos, a excepción si son nuestros propios archivos, si quisieras guardar un archivo ajeno y no dejarlo en cache tendrías que hacerlo de la siguiente forma.

```
ipfs pin add /ipfs/QmSRkkgJjfp2EisqBCtwijwVKPg98qV9a4CZ8yPEbZCH44
```
Para el siguiente articulo hablare sobre IPNS, que seria la forma en que podriamos alojar nuestras paginas web estaticas usando IPFS. Si el articulo les gusto, no duden en dejar un comentario y compartirlo. Siganme en mis demas redes sociales.
