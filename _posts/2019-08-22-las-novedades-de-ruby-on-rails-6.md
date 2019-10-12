---
layout: post
title: Las novedades de Rails 6
categories:
- ruby
tags:
- Rails 6
- Ruby on Rails 6
- Novedades Rails 6
- Lo nuevo de Rails 6
- Caracteristicas de Rails 6
image: /assets/images/images_posts/rails-6.png
lang: "es-MX"
---
<p>El pasado 15 de Agosto fue liberada la nueva versión de Ruby on Rails, la cual contiene novedades interesantes en esta sexta versión del popular Framework.</p>

<p>La primer característica que trae Rails 6 está enfocada al manejo y procesamiento de los correos electrónicos entrantes, con Action Mailbox, el cual enruta los correos para procesarlos en Rails. Se envía con entradas para Amazon SES, Mailgun, Mandrill, Postmark y SendGrid. También puede manejar los correos entrantes directamente a través de las entradas incorporadas de Exim, Postfix y Qmail.</p>

<p>Ahora tenemos el soporte para múltiples bases de datos para que se puedan conectar al mismo tiempo, un beneficio que puede ayudar en el rendimiento al poder dividir la lectura y escrituras de bases de datos replicadas. Con la ventaja de una API que nos simplifica las cosas sin tener que hacer tantos malabares en Active Record.</p>

<p>Action Cable es una herramienta importante que apareció en Rails 5 y ahora en Rails 6 se ha mejorado mucho brindando un mayor rendimiento en nuestra aplicación, Action Cable Javascript ahora está escrito en ES6.</p>

<p>Una nueva función de nombre “Action Text” permite traer texto enriquecido en Rails incluyendo el editor Trix que maneja todo, desde el formato hasta los enlaces, las citas, las listas y las imágenes y galerías incrustadas.&nbsp;</p>

<p>El contenido de texto enriquecido generado por el editor Trix se guarda en su propio modelo Rich Text asociado con cualquier modelo de registro activo existente en la aplicación. Todas las imágenes incrustadas (u otros archivos adjuntos) se almacenan automáticamente usando el Almacenamiento activo y se asocian con el modelo Rich Text incluido.</p>

<p>Webpack es ahora el paquete Javascript predeterminado a través de un nuevo directorio app/javascript, esto nos puede servir mucho para mejorar significativamente nuestro front-end, aun así el equipo de desarrollo de Rails todavía usa la canalización de assets con Sprockets para CSS y assets estáticos, mencionando que ambas características funcionan bien.</p>

<p>Por último Zeitwerk es el nuevo autocargador de código para Rails 6.</p>

<p>Espero que no se me pase algún detalle importante aun así puedes leer todas las notas de esta nueva versión en la página <a href="https://edgeguides.rubyonrails.org/6_0_release_notes.html" target="_blank" rel="nofollow">“Edge Guides” de Rails</a>.</p>

<h2 class="subtitle is-2 has-text-centered has-text-weight-bold">Cosas que he descubierto usando Rails 6</h2>

<p>Lo primero que encontré al crear un nuevo proyecto en Rails 6 es que ahora  te pide que tengas instalado YARN, suponiendo que este nuevo requisito es por el detalle que ya viene integrado con webpack, ademas que todos nuestros archivos javascript dentro del proyecto ya no se encuentran en app/assets/javascript, sino que todo se movió a app/javascripts, donde podremos precargar el webpack que necesitemos.</p>

<p>Queriendo probar <strong>Action Text</strong>,<strong> </strong>ya que se me hizo de las mejores innovaciones, de requisito nos va a pedir que usemos <strong>Active Storage </strong>y dos gemas extra: <strong>"</strong>image_processing" y "mini_magick" por el procesamiento de imágenes que lleguemos a usar en <strong>Trix editor</strong>.</p>

<p>Desde mi punto de vista personal encuentro a Rails 6 mas rapido que la versión anterior al momento de hacer pruebas en el modo "development" esta podía tardar mucho al cargar la pagina y mostrarme posibles errores, cosa que ahora suele mostrarme casi de inmediato.</p>

<hr class="wp-block-separator"/>

Aun es muy pronto para conocer todos los detalles que tiene Rails 6, pero ya empece a usarlo por lo que pronto se los iré compartiendo, ademas recuerden que estoy publicando [tutoriales de programación en Ruby]({%post_url 2019-05-06-tutorial-ruby-01 %}) con la intención de llegar a hacer con Ruby on Rails, ahora que existe esta nueva versión iremos directamente a trabajar con esta versión y así ir conociendo todo aspecto que podremos usar.
