---
layout: post
title: 'Tutorial Ruby #04 Arreglos y Hash'
categories:
- programación
- ruby
tags: 
- Ruby
- Ruby on Rails
- rails 6
image: /assets/images/images_posts/Ruby-Tutorial-04.png
lang: "es-MX"
---
Seguimos con los tutoriales de ruby, veremos el funcionamiento de los Arreglos y Hash

<h2 class="subtitle is-2 has-text-centered has-text-weight-bold" >Arreglos</h2>

<p>Los arreglos es algo que usamos mucho en los diferentes lenguajes de programación que llegamos a manejar y obviamente Ruby no seria la excepción. En ruby tenemos diferentes formas de declarar arreglos y tambien de manipularlos.</p>

<p>Para declarar una matriz, arreglo, array o como quieran llamarlo tenemos varias opciones, con las que mas estoy acostumbrado son las siguientes</p>

<pre class="wp-block-code"><code>#Crear un objeto array
arreglo = Array.new
#Crear un objeto array pero con el numero de elementos que tendra
arreglo2 =Array.new(2)
#Simplemente iniciarlo con corchetes
arreglo3 = []
#Iniciarlo con los elementos que tendra
arreglo4 = ["Jesus","Leonel","Emmanuel"]</code></pre>

<p>Un gran cambio que podemos notar con los arreglos en Ruby es la forma en recorrer los elementos del mismo, mientras que en otros lenguajes tendriamos que hacerlo con un&nbsp;<strong>For.</strong></p>

<pre class="wp-block-code"><code>arreglo4.each do |indice|
    puts indice
end</code></pre>

<p>Nos creamos una variable "indice" donde se almacena temporalmente cada elemento de nuestro arreglo para los usos que queramos darle</p>

<h2 class="subtitle is-2 has-text-centered has-text-weight-bold">Hash</h2>

<p>Los hash son como los arreglos pero con una gran diferencia, ya que en vez de existir un indice en el que se recorra el elemento, estos contendran llaves que sirvan para poder localizar el elemento que queramos usar.</p>

<p>La forma en que las declaramos es casi igual que con los arreglos solo que en vez de corchetes ([ ]) usamos las llaves ({ })</p>

<pre class="wp-block-code"><code>hash.= Hash.new
hash2 = {}

#Lo llenamos de la siguiente forma
hash2 = {"Nombre" => "Jesus","apellido" => "Figueroa"}</code></pre>

<p>Recorrerlo tambien podemos hacerlo con el metodo&nbsp;<strong>each</strong></p>

<pre class="wp-block-code"><code>hash2.each do |llave,elemento|
    puts llave
    puts elemento
end</code></pre>

