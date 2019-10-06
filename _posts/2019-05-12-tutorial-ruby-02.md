---
layout: post
title: 'Tutorial: Programación en Ruby #02 - Variables'
categories:
- programación
- ruby
tags:
- Tutorial Ruby
- Ruby on Rails
cabecera: /assets/images/images_posts/Ruby-Tutorial-02.png
---
Una vez que tenemos instalado Ruby en nuestra computadora es momento de pasar un poco mas a la practica, aunque podemos usar el <strong>IRB</strong> para nuestras practicas, yo les recomiendo que usen un <strong>IDE</strong> como puede ser <strong>Atom, Sublime Text, Visual Studio Code, entre otros.</strong>

Tomen el de su preferencia, con el que estén mas acostumbrados para trabajar. Cada archivo con el que se programaba en Ruby se guarda con la extensión <strong>".rb"</strong> de esa forma desde la terminal de comandos pueden ejecutar su programa escribiendo solamente.  <strong>ruby &lt;nombredelprograma&gt;.rb</strong>

<h2 class="subtitle has-text-centered is-size-3 has-text-weight-bold">Variables</h2>
<p>Una de las características que tiene Ruby, es que las variables no son necesarias declararlas con un tipo de especifico, como suele ser en algunos otros lenguajes como lo que es C++, Java, etc. Las variables cambian de tipo en tiempo de ejecución por lo que por un momento puede ser una variable de tipo entero y en otro se vuelve una variable de tipo cadena, dependiendo de como las estemos usando al momento de necesitarlas.</p>
<h3 class="subtitle">Tipos de Variables</h3>
<h4 class="subtitle">Variables locales</h4>
<p>Tienen un ámbito local (dentro de una función o contexto) por convención se escriben en minúscula y si tiene un nombre compuesto este se separa por un guion bajo.</p>
<pre class="wp-block-code"><code>nombre, id_cliente, primer_apellido, segundo_apellido</code></pre>
<h4 class="subtitle">Variables Globales</h4>
<p>Tienen un ámbito global (usados en cualquier parte de nuestro código, empiezan con el símbolo <em>$</em> conservan la misma convención de las variables locales.</p>
<pre class="wp-block-code"><code> $nombre, $id_cliente, $primer_apellido, $segundo_apellido</code></pre>
<h4 class="subtitle">Constantes</h4>
<p>Variable que nunca cambiara de valor en todo el programa, por convención siempre se escriben en mayúscula.</p>
<pre class="wp-block-code"><code>PI, CAPACIDAD</code></pre>
<h4 class="subtitle">Variables de Instancia</h4>
<p>Aunque lo veremos mas adelante cuando se vean <em>Clases</em> son las variables que se ejecutan dentro de una clase y son las variables que tendrá un objeto, cuando se crean sin iniciarse/usarse en un método estas tendrán el valor de null, se representan colocando un <em>@</em> antes del nombre de la clase.</p>
<pre class="wp-block-code"><code>@nombre, @edad</code></pre>
<h4 class="subtitle">Variables de clase</h4>
<p>Variables que pertenecen a la clase que tiene la facultad de que la variable al ser cambiado su valor, todos los objetos de esa clase también cambiara el valor de esa variable, por eso es obligado que cuando se crea una variable de este tipo debe comenzar inicializada con un valor y se representan con <em>@@</em> antes del nombre de la clase.</p>
<pre class="wp-block-code"><code>@@ruedas = 4</code></pre>
<h2 class="subtitle has-text-centered is-size-3 has-text-weight-bold">Hola mundo en Ruby</h2>
<p>En su IDE de preferencia creamos un fichero que termine con la extensión <strong>".rb"</strong> y en el archivo basta con poner:</p>
<pre class="wp-block-code"><code>puts "hola mundo"</code></pre>
<p>No es necesario poner nada mas, tendremos nuestro programa guardado, para ejecutarlo solo es cuestión de colocar en nuestra terminal <strong>"ruby &lt;nombre_del_archivo>".</strong></p>
<p>Con esto vamos empezando a programar en Ruby, en el siguiente articulo hablare sobre las Estructuras de decisión y Bucles</p>
