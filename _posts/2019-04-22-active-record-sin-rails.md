---
layout: post
title: Active Record sin Rails
categories:
- programación
- ruby
tags:
- Tutorial Ruby
- Ruby on Rails
cabecera: assets/images/images_posts/Ruby-Active-Record-sin-Rails.png
---
Uno de los lenguajes de programación que mas me atraen es sin duda&nbsp;<strong>Ruby,</strong>&nbsp;sobretodo con su<strong>&nbsp;Framework Rails</strong>&nbsp;en la que puedes hacer sitios poderosos y rápidos. Pero una de las características que desde mi punto personal es la mas fuerte de Rails es sin duda&nbsp;<strong>Active Record</strong>&nbsp;que nos permite manipulas bases de datos directamente desde el codigo y es la parte del "Modelo" en el MVC que es Rails.

Pero quitando Rails, usando Ruby puro (sobretodo para un bot en Telegram que estoy haciendo y otro para Steem) me preguntaba como usar esta gema&nbsp;<strong>"Active Record"</strong>. Investigando un poco me di cuenta que era solo cuestión de instalarla en tu Gemfile.

<code>gem "activerecord"</code>

Sin embargo el problema que tuve fue que no podía generar mis migraciones ni modelos, así que las estuve agregando las instrucciones a mi Rakefile, las cuales compartiria sino me diera cuenta que perdi mi tiempo, porque despues me entere que existia otra gema que hacia justamente lo que queria.

## [standalone-migrations](https://github.com/thuss/standalone-migrations){:target='_blank'}
{: .subtitle .has-text-centered .is-size-3 has-text-weight-bold} 

Standalone Migrations hace exactamente lo que quería, el poder usar Active Record fuera de proyectos Rails con la ventaja que se mantiene actualizado, pues incluso están añadidas las características que se pueden hacer en Rails 5

Para instalarlo es cuestion de poner en tu Gemfile el siguiente comando:
<code>gem 'standalone_migrations'</code>
Y en el Rakefile:

~~~ruby
require 'standalone_migrations'
StandaloneMigrations::Tasks.load_tasks
~~~

Su uso es prácticamente igual a como si estuviéramos usando Rails, con la única diferencia al momento de generar una migración, sin ser un problema el cambio pues su&nbsp;<strong>README</strong>&nbsp;esta bien documentado para que podamos realizar nuestras migraciones sin problema alguno.

Para mi Active Record es una de las mejores librerías para manejar base de datos y digo "librerías" porque no he encontrado algo parecido para algún otro lenguaje de programación.