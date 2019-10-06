---
layout: post
title: 'Tutorial Ruby #05 Clases y Metodos'
categories:
- programación
- ruby
tags:
- Tutorial Ruby
- tutorial ruby on rails
- ruby como programar
cabecera: assets/images/images_posts/Ruby-Tutorial-05.png
---
<p>Es momento de que profundicemos mas con el lenguaje de Ruby y empezaremos con crear nuestras clases, métodos y entender su estructura. Recordemos que esto no es un tutorial sobre Programación Orientada a Objetos por lo que no se profundizara en el tema pero que es muy importante que lo conozcan para que no se pierdan.</p>

<p>Las clases en Ruby son muy fáciles de declarar y flexibles al usarse en diferentes métodos pues recordemos que para Ruby todo es considerado objeto mientras que en otros lenguajes no necesariamente. (Ejemplo: en c++ una variable tipo Int no es considerado objeto mientras que una variable en Ruby que tenga un entero si es considerado un objeto).</p>

<pre class="wp-block-code"><code>class Persona
    def saludar
        puts "Hola a todos"
    end</code></pre>

<p>Podemos llamar a dos objetos diferentes de clase bajo una función y mientras ambos objetos tengan los mismos métodos no ocasionara ningún error. De esas forma podemos mostrar que tan flexible es Ruby. </p>

<pre class="wp-block-code"><code>class  Perro
    def  sonido
        puts  "Guau Guau"
    end
end
class  Gato
    def  sonido
        puts  "miau miau"
    end
end
def  hacer_sonido(clase)
clase.sonido
end
perro  =  Perro.new
hacer_sonido(perro)
gato  =  Gato.new
hacer_sonido(gato)</code></pre>

<p> Para nuestras variables que se encuentren dentro los métodos de clase usaremos el "@" antes del nombre de nuestra variable, si lo vemos en analogía, este símbolo es el equivalente a&nbsp;<code>this</code>en otros lenguajes de programación.</p>

<pre class="wp-block-code"><code>class Persona
    def initialize(nombre)
        @nombre = nombre
    end
end
persona = new Persona("Shadow Myst")</code></pre>

<p>Otro detalle que coloque aqui es la palabra&nbsp;<code>initialize</code>&nbsp;que es una palabra reservada que nos crea un "constructor" para nuestra clase, en otras palabras, es método que se "correrá" cuando creamos el objeto de una clase.</p>

<p>Es normal que cuando creamos métodos para modificar o mostrar atributos en nuestras clases, los hagamos de dos formas, los que usamos para modificar "set" y los que usamos para mostrar "get", y en Ruby como la intención es siempre parecerse al lenguaje humano, podemos facilitarnos mas las cosas.</p>

<pre class="wp-block-code"><code>#Ejemplo de Metodo set y get
class Persona
 def initialize(nombre,edad)
  @nombre = nombre
  @edad = edad
 end
#Metodos para visualizar
 def nombre
   @nombre
 end
 def edad
   @edad
 end
#Metodos para visualizar atributos
 def nombre=(nombre)
   @nombre = nombre
 end
 def edad=(edad)
   @edad = edad
 end
end

persona = Persona.new("Leonel",22)
#mostrar datos
persona.nombre
persona.edad
#modificar datos
persona.nombre="Emmanuel"
persona.edad=17</code></pre>

<p>De esta forma al usar un "=" al escribir nuestros métodos "set" lo podemos asemejar a una asignación de una variable, de igual forma se pueden usar símbolos en nuestros métodos.</p>

<p>Para el siguiente tutorial hablare sobre herencia. Ya estamos mas cerca de hablar sobre su framework mas conocido <strong>Rails</strong></p>
