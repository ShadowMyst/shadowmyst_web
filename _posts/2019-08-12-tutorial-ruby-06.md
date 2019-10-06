---
layout: post
title: 'Tutorial Ruby #06: Herencia'
categories:
- programación
- ruby
tags:
- Tutorial Ruby
- tutorial ruby on rails
- ruby como programar
cabecera: /assets/images/images_posts/Ruby-Tutorial-06.png
---
<p>Una de las grandes ventajas de la programación orientada a objetos es la forma en que podemos heredar atributos y métodos de clases padre, a sus respectivas clases hija, permitiendo que no tengamos que repetir código a cada rato y dándole extensibilidad a nuestros programas</p>

<p>Para este tutorial haremos dos archivos, uno que sera nuestra clase padre y otra que sera una clase hija que herede los métodos y atributos de la clase padre. En este caso haremos una clase "FiguraGeométrica" donde tendremos los atributos de base y altura para luego crear la clase hija de nombre "rectángulo" que hereda los atributos de la clase padre y ademas le agregaremos el metodo de  "área" y un archivo principal al que llamaremos "main.rb".</p>

<p>Para este ejemplo en nuestra clase padre solo crearemos el metodo contructor:</p>

<pre class="wp-block-code"><code>#Nombre del archivo figura_geometrica.rb
class FiguraGeometrica
    def initialize(base, altura)
        @base = base
        @altura = altura
    end
end</code></pre>

<p>Ahora en nuestra clase Triangulo pondremos un método para realizar el area y especificaremos que es un clase hija:</p>

<pre class="wp-block-code"><code># Nombre del archivo triangulo.rb
require 'figura_geometrica'
class Triangulo &lt; FiguraGeometrica
    def area
        @area = (@base * @altura) / 2
        @area
    end
end</code></pre>

<p>Con <strong>require</strong> estamos llamando al archivo 'figura_geometrica.rb" que tenemos en la misma carpeta, en caso de estar en otra carpeta hay que especificar bien la ruta.</p>

<p>En la siguiente linea con el símbolo "&lt;" especificamos que la clase Triangulo es hija de la clase FiguraGeometrica, no es necesario pedir los valores, ya que el constructor "FiguraGeometrica" los pide al momento de crear un objeto de la clase Triangulo que crearemos en nuestro archivo "main.rb"</p>

<pre class="wp-block-code"><code>require 'triangulo'
puts "Escribe la base: "
base = gets
base = base.chomp.to_f
puts "Escribe la altura: "
altura = gets
altura = altura.chomp.to_f
triangulo = Triangulo.new(base, altura)
triangulo.area</code></pre>

<p>Por ultimo en nuestro archivo principal, nos dedicamos a pedir los datos necesarios y luego crear el objeto "triangulo".</p>

<p>Con "gets" le pedimos un dato al usuario, mientras que con "chomp" cortamos el salto de linea "/n" y combinando con "to_f" cambiamos el valor a tipo flotante.</p>

<p>Al final creamos nuestro objeto de la clase Triangulo donde le agregamos la base y altura inicializada desde el constructor padre.</p>

<p>De igual forma podemos crear nuestro propio constructor para una clase hijo y pedir que se inicie junto al constructor padre</p>

<pre class="wp-block-code"><code>require 'figura_geometrica'
class Cuadrado &lt; FiguraGeometrica
    def initialize(base, altura, lado)
        super(base, altura)
        @lado = lado
    end
    def perimetro
        @perimetro = @lado * 4
        @perimetro
    end
    def area
        @area = @base * @altura
        @area
    end
end</code></pre>

<p>De igual forma creamos una clase Cuadrado, con la gran diferencia de que con la función "super" llamamos al constructor de la clase padre "FiguraGeometrica". De igual forma podemos sobrescribir los métodos en nuestras clases hija, si es que queremos agregar nuevas funcionalidades, según sea el caso lo podremos ver en otro tutorial.</p>