---
layout: post
title: 'Tutorial: Programación en Ruby #01'
categories:
- programación
- ruby
tags:
- Tutorial Ruby
- Ruby on Rails
- rails 6
cabecera: /assets/images/images_posts/tutorial-01-ruby.png
---
Desde hace tiempo había querido hacer tutoriales de programación en Ruby. Y aunque inicie con ellos en una de mis cuentas de Steemit, quiero que estén disponibles para el blog y el canal de Youtube desde lo mas basico y con el paso de los post ir mejorando en cuestión de complejidad. Aunque tengo un post sobre [Active Record sin Rails]({% post_url 2019-04-22-active-record-sin-rails %}) (una gema de rails), creo que seria bueno que empecemos desde cero

<iframe width="560" height="315" src="https://www.youtube.com/embed/bHoj1eoOSD4" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
{: .video}

Ruby es uno de los lenguajes a los que le tenia cierta indiferencia y que cuando lo comence a usar (por cuestiones laborales) hizo que me enamorara del lenguaje. Ruby es un lenguaje de programación orientado a objetos joven, siendo que salio a la luz en 1995 y es ampliamente conocido por su <strong>Framework Rails

Como mencione Ruby es un lenguaje POO (Programación Orientada a Objetos) que prácticamente considera todo como un objeto incluyendo el atributo "nil" (nulo) como un objeto de la clase "NilClass" con sus respectivos metodos, asi que si no sabes nada sobre POO, me gustaría que me lo escribieras en los comentarios y asi tener la posibilidad de crear un post y así hablar sobre el paradigma orientado a objetos.

Bien mi intención es hablar puramente de Ruby al principio y cuando llegue el momento adecuado dividir los temas en dos: <strong>Ruby on Rails</strong> para hacer aplicaciones web y <strong>Ruby con GTK</strong> porque Ruby no es un lenguaje que solo funcione para web, hay mucho material para Ruby que no ha sido explotado.

## Instalación de Ruby
{: .subtitle .has-text-centered .is-size-3 .has-text-weight-bold} 

### Instalar Ruby en Windows 10
{: .subtitle}

Como recomendación y por ser futuros programadores es tener una distribución Linux disponible, porque aunque Ruby se puede manejar en Windows al final del día tendrás muchos problemas al momento de usarlo, como que algunas gemas no funcionan, aunque espero que en un futuro se vuelva realmente un software multiplataforma.

La simpleza de Windows al momento de instalar programas ha hecho que la instalación de Ruby sea a través de puros clics al botón <strong>"siguiente"</strong>, podemos optar por dos opciones para instalar.  Descargar Ruby desde la pagina oficial <a rel="noreferrer noopener" aria-label=" (opens in a new tab)" href="https://www.ruby-lang.org/es/" target="_blank" rel="nofollow">ruby-lang</a> o desde <a href="http://railsinstaller.org/en" target="_blank" rel="nofollow" aria-label=" (opens in a new tab)">RailsInstaller</a> para una vez tener instalado el Framework rails. Durante mucho tiempo me causo problemas Rails en Windows pero logre solucionarlo con un simple truco que veremos en futuros post (o si necesitan la respuesta de inmediato diganme en los comentarios).

### Instalar Ruby en Linux con RVM
{: .subtitle}

Las ventajas de instalar Ruby usando RVM, es que podemos acceder rápidamente a diferentes versiones de Ruby en las que queramos trabajar, esto nos sirve para cuando tenemos que trabajar con gemas que requieran una versión especial de Ruby para funcionar.

Las instrucciones en terminal son las siguientes: 
```
\curl -sSL https://get.rvm.io | bash -s stable
```

Continuamos cargando RVM, como una función de nuestro Shell
```
source ~/.rvm/scripts/rvm
```

Terminado de instalar RVM, ya solo es cuestión de instalar la versión de Ruby con la que necesitemos trabajar

```ruby
rvm list known //Para saber las versiones disponibles a instalar
rvm install <version_a_instalar>
rvm --default use <version> //Version que usaremos principalmente
```

Una vez instalado podemos comprobar que todo este en orden si en  nuestra terminal de comandos colocamos "irb" y nos dara acceso al  interprete interactivo de Ruby

![](assets/images/images_posts/irb.png){: .image .is-512 .image-centered}

Instalar Rails es tan fácil como poner en nuestra terminal "gem install rails" pero en post posteriores hablaremos sobre este Framework, por el momento me enfocare puramente a Ruby y como se vayan progresando en los post es como llegaremos a crear nuestras paginas web con este servicio