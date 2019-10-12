---
layout: post
title: 'Tutorial Ruby #03 Estructuras de decisión y Bucles'
categories:
- programación
- ruby
tags: 
- Ruby
- Ruby on Rails
- rails 6
image: /assets/images/images_posts/Ruby-Tutorial-03.png
lang: "es-MX"
---
<p><br>Continuando con los <a href="https://shadowmyst.net/programacion-ruby-02/">tutoriales</a> de programación Ruby hablaremos ahora con las estructuras de control que nos brinda este lenguaje de programación.</p>

<p>Una de las ventajas y al mismo tiempo un poco confuso para los programadores experimentados es que en Ruby no se usan llaves <em>"{" "}</em>" en nuestro ámbito de programación, ni tampoco terminamos nuestras instrucciones con un ";".</p>

<h2 class="subtitle is-2 has-text-centered has-text-weight-bold">Condicionales</h2>

<h3 class="subtitle is-3">If/else y unless</h3>

<p>Ruby tiene algo mas que el <strong>if/else</strong> como condicional primaria, sino que también tenemos a <strong>unless</strong>, mientras que <strong>If</strong> analiza una condición verdadera y de ahí sigue el flujo de instrucciones, <strong>unless</strong> hace justamente lo opuesto, analiza una condicional y si es falsa se ejecutan las instrucciones dentro del ámbito.<br> <strong>Ejemplo de if:</strong></p>

<pre class="wp-block-code"><code>a  =  5
b  =  7
if a&lt;b
    puts  "a es menor de b"
else
    puts  "b es menor de a"
end</code></pre>

<p>En este caso como a es menor que b por lo que la condicion es verdadera nos imprimirá el mensaje dentro del if<br> <strong>Ejemplo unless:</strong></p>

<pre class="wp-block-code"><code>a  =  5
b  =  7
unless a&lt;b
    puts  "b es menor de a"
else
    puts  "a es menor de b"
end</code></pre>

<p>Pero en este caso como <strong>unless</strong> necesita que la condición sea falsa, nos va a imprimir lo que esta dentro de <strong>else</strong>. También podemos poner nuestro condicional en una sola instrucción si es que nuestro programa es algo simple.</p>

<pre class="wp-block-code"><code>puts "a es menor a b" if a &lt; b
puts "b es menor a a" until a &lt; b</code></pre>

<h3 class="subtitle is-3">Switch/Case</h3>

<p>Aunque en otros lenguajes de programación lo conocemos como un <strong>"switch"</strong> aqui se usa la palabra reservada <strong>"case"</strong> y su uso es prácticamente igual.</p>

<pre class="wp-block-code"><code>case calificacion
    when (0..69) #Esta es una variable del tipo Range
        puts "Reprobado"
    when (70..100)
        puts "Aprobado"
    else
        puts "No existe esa calificación o fue mal escrita"
end</code></pre>

<p>NOTA 1: Los comentarios de una sola linea podemos anteponerlos con <strong>"#"</strong><br> NOTA 2: Dentro de nuestro <strong>Case</strong> podemos usar variables de tipo string, numéricos o en el caso de este ejemplo usamos de clase <strong>Range</strong><br> NOTA 3: Mientras que en otros lenguajes se usa <strong>default</strong> como opción final en cuanto no tengamos como evaluar, en ruby usaremos <strong>Else</strong> como si fuera un if.</p>

<h2 class="subtitle is-2 has-text-centered has-text-weight-bold">Bucles</h2>

<p>Ruby también nos da una variedad de diferentes palabras reservadas para usar bucles aparte de las tradicionales <strong>while, do-while y for</strong>, veamos todas una por una en un ejemplo rápido</p>

<h3 class="subtitle is-3">While, Do-while y until</h3>
<p><!-- /wp:heading --></p>
<p><!-- wp:paragraph --></p>

<h4 class="subtitle is-4">While</h4>
<pre class="wp-block-code"><code>while a&lt;10
    puts a
    a+=1
end</code></pre>

<h4 class="subtitle is-4">do-while</h4>

<p>Realmente no se conoce como do-while en ruby pero como es lo mas parecido a otros lenguajes lo subtitule de esa forma</p>

<pre class="wp-block-code"><code>begin
    puts a
    a+=1
end while a&lt;10</code></pre>

<h4 class="subtitle is-4">until</h4>

<p>Until es lo mismo que cuando vimos <strong>unless</strong> mientras la condición sea falsa se va a cumplir la condicion</p>

<pre class="wp-block-code"><code>until a&lt;10
    a+=1
    puts "a no es menor a 10"
end
---------------
begin
    puts "a no es menor a 10"
    a+=1
end until a&lt;10</code></pre>

<p>De igual forma podemos poner nuestro <strong>while</strong> y <strong>until</strong> en una sola instrucción.</p>

<pre class="wp-block-code"><code>a+=1 while a&lt;20 #Para While
a+=1 until a>20 #Para Until</code></pre>

<h3 class="subtitle is-3">Loop</h3>

<p>Cuando conocí <strong>Loop</strong> se me hizo extraño pues realmente consiste de ciclar una instrucción indefinidamente y la única forma de salirse es con la palabra reservada <strong>break</strong></p>

<pre class="wp-block-code"><code>loop do
    puts a
    a+=1
    break if a>100
end</code></pre>

<h3 class="subtitle is-3">For</h3>

<p>Por ultimo nos falta la instrucción For que se nos simplifica mucho mas, aunque al principio puede confundir</p>

<pre class="wp-block-code"><code>for i in (0..10)
    puts i
end</code></pre>

<p>Mientras que en otros lenguajes usamos la sintaxis <code>for(i=0;i&lt;10;i++)</code> con Ruby lo reducimos a el nombre de la variable y de donde a donde sera su intervalo.</p>

<p>Por ultimo y como recordatorio, podemos usar cuatro comandos que nos ayudaran en nuestros bucles</p>

<ul>
<li>break: Termina el bucle</li>
<li>next: Se adelanta a la siguiente interacción del bucle</li>
<li>redo: Se repite el bucle ignorando anulando la evaluación de la condición</li>
<li>retry: Se repite el bucle repitiendo de igual forma la evaluación de la condición</li>
</ul>

<p>Existen otros tipos de bucles que podemos encontrar en este lenguaje pero las veremos en futuros tutoriales, con que se aprendan estas principales sera mas que suficiente (por ahora).</p>

<p>Espero que les guste estos tutoriales y de serlo, espero que lo puedan compartir,</p>

