---
layout: post
title: Como ser Witness en Creary
categories:
- criptomonedas
- Tecnología
tags:
- creary wtiness
- creary
- como ser testigo en creary
cabecera: /assets/images/images_posts/creary.png
---
<p>Para los que me conocen saben que soy fanático de las criptomonedas y uno de los proyectos que mas me gustan es el de la criptomoneda <a rel="noreferrer noopener" aria-label="Creary (opens in a new tab)" href="https://creary.net" target="_blank">Creary</a> que he seguido desde sus inicios como Creativecoin. Y como usa una blockchain como Steemit, no quería esperar para convertirme en Witness.</p>

<p>Un witness (testigo) es un usuario que ayuda a que la red de una blockchain (en este caso CREA) se mantenga a flote, ademas que representa a todos los usuarios que le dan su voto y confianza que los represente en la red. El servidor de un witness debe estar en funcionamiento todo el tiempo, por lo que debe ser confiable para que la red se mantenga estable.</p>

<p>El posicionamiento de un testigo se define por los usuarios que lo votan y en crea los primeros 24 testigos posicionados producen bloques y firman transacciones, mientras que del 25 en adelante es seleccionado al azar en cada ronda para producir dichos bloques.</p>

<p>Hay que recordar que para ser testigo debes tener conocimientos de programación y mas que nada saber gestionar y dar mantenimiento a tu servidor, pero en cualquier cosa puedo brindarte ayuda en el proceso o puedes consultar la comunidad en Discord de la comunidad de Creary.</p>

<p>Antes de comenzar, te invito a votar por belial2412, chibido y por mi shadowmyst como testigo en <a rel="noreferrer noopener" aria-label="https://creary.net/~witness (opens in a new tab)" href="https://creary.net/~witness" target="_blank">https://creary.net/~witness</a> ya que los tres estamos votando los post interesantes ademas de desarrollar Dapps para la comunidad en Creary.</p>

<p>Por ultimo quiero agradecer a Andersson (CTO/Blockchain Core de Creary) por las asesorias que me dio para poderme volver Witness.</p>

<h2 class="subtitle is-2 has-text-centered has-text-weight-bold">Configurar nuestro nodo con Docker y anunciar nuestro usuario como Witness)</h2>

<h3 class="subtitle is-3">Tener un VPS</h3>

<p>Recordemos que como debe ser un servidor conectado y prendido 24/7, es mejor que compremos un VPS como recomendación <a rel="noreferrer noopener" aria-label="OVH (opens in a new tab)" href="https://www.ovh.com/" target="_blank">OVH</a>, <a rel="noreferrer noopener" aria-label="Contabo (opens in a new tab)" href="https://contabo.com/" target="_blank">Contabo</a> que son con las que he trabajado y el VPS debe tener como mínimo las siguientes características.</p>

<p> CPU: Dual core @ 2GHz o superior por núcleo.<br>Memory: 4GB (8 GB para estar preparado para el futuro)<br>Bandwidth: 1 Gbit/s<br>Storage: Minimo , 25 GB. Recomendado 50GB para el futuro. </p>

<h3 class="subtitle is-3">Un poco de seguridad con el SSH</h3>

<p>Para protegernos un poco de los ataques es recomendable que en nuestro VPS quitemos el acceso SSH por contraseña y que sea solo nuestro equipo con el que pueda acceder.</p>

<p>Para esto creamos una llave SSH protegida por contraseña con el siguiente comando:</p>

<pre class="wp-block-code"><code>ssh-keygen -t rsa -b 4096 -C "your_email@example.com"</code></pre>

<p>Copia el contenido de <em>~/.ssh/id_rsa.pub&nbsp;</em>en una línea en ~/.ssh/authorized_keys en tu servidor o usa el comando: </p>

<pre class="wp-block-code"><code>ssh-copy-id &lt;user>@&lt;ip-server></code></pre>

<p>Prueba la conexión usando la clave publica SSH. Esto es vital para desconectar el inicio de sección con contraseña.</p>

<p>Una vez comprobado esto, hay que desactivar la comprobación por contraseña del SSH. Edita el archivo /etc/ssh/sshd_config, busca la linea #PasswordAuthentication yes y cámbiala por PasswordAuthentication no. Guarda los cambios y reinicia el servicio ssh:</p>

<pre class="wp-block-code"><code>sudo service ssh restart</code></pre>

<h3 class="subtitle is-3">Anunciarte como Witness</h3>

<p>Tenemos que empezar a anunciarnos en la blockchain como witness, para ello tenemos que instalar NodeJS usando NVM, para ello podemos seguir las intrucciones encontradas en <a rel="noreferrer noopener" aria-label="https://github.com/nvm-sh/nvm (opens in a new tab)" href="https://github.com/nvm-sh/nvm" target="_blank">https://github.com/nvm-sh/nvm.</a> Y una vez instalado NVM, la versión de NodeJS que pondremos sera la 10.15.3, esto haciendolo como Root, ya que docker funciona como root.</p>

<p>Cuando lo tengamos instalado, instalaremos una herramienta de Creativechain que encontraremos en <a rel="noreferrer noopener" aria-label="https://github.com/creativechain/creary-tools/wiki/Witness-Tools (opens in a new tab)" href="https://github.com/creativechain/creary-tools/wiki/Witness-Tools" target="_blank">https://github.com/creativechain/creary-tools/wiki/Witness-Tools</a> o para mas fácil con el comando:</p>

<pre class="wp-block-code"><code>npm install -g @creativechain-fdn/creary-tools</code></pre>

<p>Este es un proyecto que provee de comandos utiles para varios tipos de usuarios en crea y el cual usaremos justamente para anunciarnos como Witness. Una vez instalado pasamos con el siguiente comando</p>

<pre class="wp-block-code"><code>crea-witness update &lt;MiClaveActivaPrivada> &lt;nombretestigo> &lt;nombreusuario> "&lt;enlacePromociondelTestigo>" &lt;ClavePublicaParaFirmarBloques> &lt;props></code></pre>

<p>Lo explico para que no se hagan vueltas:</p>

<ul>
<li>MiClaveActivaPrivada: La encontraran en su perfil de creary en la seccion de permisos y dandole en "show private key" de la seccion "active"</li>
<li>nombretestigo: Es el nombre que le pondremos al testigo</li>
<li>nombreusuario: Es nuestro nombre de usuario por lo general se repite con el nombre de testigo ejemplo de mi caso "shadowmyst shadowmyst"</li>
<li>EnlacePromociondelTestigo: Puede ser tu perfil de creary o en mi caso mi pagina web</li>
<li>ClavePublicaParaFirmarBloques: De igual forma puedes usar tu clave publica activa (ya no la privada)</li>
<li>props: Son argumentos extra que meteremos</li>
</ul>

<p>Al final debe quedar algo parecido a esto:</p>

<pre class="wp-block-code"><code>crea-witness update MiClaveActivPrivada shadowmyst shadowmyst "https://creary.net/@shadowmyst" MiClavePublicaParaElTestigo '{"account_creation_fee":"0.010 CREA","maximum_block_size":65536,"cbd_interest_rate":1000}' '0.010 CREA' --node https://nodes.creary.net</code></pre>

<p>En caso de que falle ejecuta:</p>

<pre class="wp-block-code"><code>npm install -g @creativechain-fdn/creary-tools@0.6.1</code></pre>

<h3 class="subtitle is-3">Bajar la ultima version de Creary con Docker</h3>

<p>Una vez que hemos sido anunciados como Witness, es momento de instalar el nodo de CREA, para ello usaremos Docker y así no tener la necesidad de andar compilando todo el nodo.<br><br>Para ello podemos instalar docker-ce y seguir las instrucciones que encontraremos <a rel="noreferrer noopener" aria-label="aquí (opens in a new tab)" href="https://docs.docker.com/install/linux/docker-ce/ubuntu/" target="_blank">aquí</a>, una vez instalado ejecutaremos un script el cual agradezco a Andersson que me lo haya proporcionado.</p>

<pre class="wp-block-code"><code>#!/bin/bash

WITNESS=$1
KEY=$2
IF=$3
CNAME=$4

docker stop node$CNAME
docker rm node$CNAME

#rm -rf /root/miners/$CNAME
#mkdir -p /root/miners/$CNAME/blockchain
#mkdir -p /root/miners/$CNAME/creawallet

docker run -d --name node$CNAME --env CREAD_WITNESS_NAME=$WITNESS --env CREAD_PRIVATE_KEY=$KEY --env NODE_UPDATER=https://crea.owldevelopers.site --env CREAD_SEED_NODES=173.212.209.206:1776 --env USE_FULL_WEB_NODE=true -v /root/miners/$CNAME/creawallet:/var/creawallet -v /root/miners/$CNAME/blockchain:/var/lib/cread/blockchain -p $IF:1776:1776 -p $IF:1886:1886 -p $IF:1996:1996 --restart always -t creary/crea:latest</code></pre>

<p>Lo guardamos con el formato .sh y procedemos a ejecutarlo, procurando que si es la primera ejecución quitemos los "#" en la parte de mkdir ya que se crearan las carpetas donde estará nuestro nodo. Como segunda nota, la parte donde dice "USE_FULL_WEB_NODE=true" esto es por si vas a hacer llamadas al nodo sobre contenido, likes, autores, etc…, deberas dejarlo en true si quieres montarte una dapp, de lo contrario podremos cambiarlo a false o simplemente quitarlo.</p>

<p>para ejecutarlo seria de la siguiente manera</p>

<pre class="wp-block-code"><code>nombrearchivo.sh nombretestigo claveprivadatestigo ipdelvps nombrecontenedor</code></pre>

<p>Y listo tendremos nuestro nodo corriendo que tardara en sincronizarse con los demás nodos dependiendo de lo grande que sea la blockchain y el poder de nuestro VPS, en mi caso tarde de 4 a 5 horas en que se sincronizara.</p>

<p>Si tienen dudas déjenlo en los comentarios y tratare de resolverlas</p>
