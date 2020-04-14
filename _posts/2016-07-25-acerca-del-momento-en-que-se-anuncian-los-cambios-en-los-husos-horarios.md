---
layout: post
title:	"Acerca del momento en que se anuncian los cambios en los husos horarios"
date:	2016-07-25 21:59:40 -0300
author:	Mariano Absatz (el Baby)
categories:	tecnología 'time & date'
---

> **[Matt Johnson](https://twitter.com/mj1856)** escribió en abril de 2016 
[On the Timing of Time Zone Changes](http://codeofmatt.com/2016/04/23/on-the-timing-of-time-zone-changes/) 
en su [blog](http://codeofmatt.com/) y 
[me autorizó a traducirlo y publicarlo](http://mm.icann.org/pipermail/tz/2016-April/023593.html).

¿Qué tienen en común Turquía, Chile, Rusia, Venezuela, Azerbaiyán, Corea del 
Norte y Haití? **¡Caos con el cambio de hora!** 

No, no es el remate de un chiste. Es un problema grave en realidad. El mayor 
problema con los husos horarios no es que existan, ni que haya horas de ahorro 
de energía en verano. Si no que estas cambien en forma completamente 
desorganizada.
<!--more-->
Déjenme explicar. 

Primero hay que comprender que desde una perspectiva global, uno podría pensar que los husos horarios del mundo deberían ser manejados por una entidad internacional relativamente neutra, como la división [UIT](https://es.wikipedia.org/wiki/Uni%C3%B3n_Internacional_de_Telecomunicaciones) de Naciones Unidas, o quizás la [UAI](https://es.wikipedia.org/wiki/Uni%C3%B3n_Astron%C3%B3mica_Internacional). Sin embargo, cada uno de los husos horarios del mundo se controlan, en realidad, desde una perspectiva local. Cada nación tiene el derecho soberano para decidir acerca de la hora local en las tierras bajo su jurisdicción. Esto incluye tanto la diferencia con la Hora Universal (UT), como las reglas que definen los cambios durante el año para el ahorro de energía, si deciden hacerlos. Esto no es un problema en sí mismo y estoy absolutamente de acuerdo con que los países deberían poder hacer lo que quieran con los relojes adentro de sus fronteras. Sin embargo, una y otra vez, nos topamos con el mismo problema, que es que **estos cambios se hacen sin una antelación suficientemente amplia**. Todos los países mencionados más arriba han hecho esto recientemente, junto con muchos otros. Es crucial que cuando los gobiernos hacen cambios a sus husos horarios o las reglas para cambiar la hora durante un período, permitan un tiempo suficiente para que la tecnología se adecue, haga pruebas a los cambios y publique y distribuya las actualizaciones. Luego hay que tener en cuenta que los individuos no siempre actualizan sus sistemas instantáneamente. Es muy común que una actualización de husos horarios esté disponible por semanas o meses antes de que el usuario final la instale efectivamente.

Caso de estudio - Turquía:
--------------------------

Tomemos a Turquía como ejemplo. En 2015 el gobierno decidió que sería una buena idea [retrasar dos semanas la finalización del cambio de hora para ahorro de energía](http://www.timeanddate.com/news/time/turkey-delays-dst-end-2015.html) para permitir más horas de luz diurna durante las elecciones. Movieron la fecha de finalización de DST (cambio de hora para ahorro de energía) del 25 de octubre al 8 de noviembre.

*   Lo primero que se supo acerca de esto fue a través de una [nota periodística no oficial](http://www.sozcu.com.tr/2015/gunun-icinden/saatler-ne-zaman-geri-alinacak-yaz-saati-uygulamasi-ne-zaman-bitecek-930383/) publicada el 8 de septiembre, alrededor de 6 semanas antes de que se debieran cambiar los relojes. Sin embargo, el artículo recién fue registrado por la comunidad TZ alrededor del 19 de septiembre. Es difícil basarse solamente en notas periodísticas, ya que muchas veces son confusos o contienen errores. Unas pocas palabras de un político a un periodista simplemente no son suficiente.
*   El 29 de septiembre, una agencia del gobierno [también reportó el cambio](http://aa.com.tr/tr/turkiye/yaz-saati-uygulamasi-8-kasimda-sona-erecek/362217). Todavía no era _completamente_ oficial, ya que no hacía referencia a ningún tipo de decreto o legislación. Pero era suficiente para convencer a algunos en la comunidad TZ de que era real y por lo tanto se comenzó a configurar un cambio en la [IANA TZ database](https://es.wikipedia.org/wiki/TZ_Database) y [se publicó unos días después, el 1° de octubre](http://mm.icann.org/pipermail/tz-announce/2015-October/000034.html).
*   El anuncio definitivo del gobierno finalmente salió el 4 de octubre cuando se publicó [en la Gaceta Oficial](http://www.resmigazete.gov.tr/eskiler/2015/10/20151004-1.htm). Esto es alrededor de tres semanas de antelación _oficial_ de la propuesta de cambio.
*   Muchos proveedores de tecnología, incluyendo a los grandes como Apple, Google y Oracle, tomaron los datos de IANA y los publicaron a través de sus propios canales. Por ejemplo, Apple lo lanzó para dispositivos iPhone y iPad con la actualización iOS 9.1 el 21 de octubre, dejando sólo 3 días para que los usuarios instalen la actualización para evitar que sus relojes cambien la hora el día incorrecto.
*   Para Microsoft Windows que sigue un procedimiento levemente diferente y requiere de un mayor grado de confirmación, [se hizo un anuncio el 9 de octubre](https://blogs.technet.microsoft.com/dst2007/2015/10/09/upcoming-windows-dst-update-for-turkey-democratic-peoples-republic-of-korea-and-fiji/) y [se publicó la actualización el 20 de octubre](https://support.microsoft.com/kb/3093503).
*   En algunos casos, la fecha se pasó por completo, como en el caso de [pytz](https://pypi.python.org/pypi/pytz) - la popular biblioteca de manejo de husos horarios para el lenguaje Python, que publicó su versión 2015.7 el 26 de octubre.

Entonces ¿cuál fue el resultado? Bueno, [citando a la BBC](http://www.bbc.com/news/world-europe-34631326):

> Turcos confundidos se preguntan "¿qué hora es?" luego de que los relojes automáticos desafiaran una decisión del gobierno para posponer el cambio de hora estacional.

O como [reportó el IBT](http://www.ibtimes.co.uk/what-time-it-now-turkeys-clocks-defy-time-change-confuse-millions-people-1525625):

> Millones de turcos se despertaron en una mañana confusa el domingo ... ya que teléfonos inteligentes, tabletas, y computadoras habían cambiado la hora automáticamente del mismo modo que otros países en el huso horario de Europa Occidental (_Eastern European Time zone_), aun cuando Turquía retrasó el cambio de hora para dos semanas más adelante.

Como se podrán imaginar, esto tuvo en la votación exactamente el efecto opuesto a lo que el gobierno había intentado lograr. Sin embargo, podrían haberlo previsto ya que ¡pasó exactamente lo mismo el año anterior! como [lo reportó la Agencia de Noticias Independientes de los Balcanes en 2014](http://www.balkaneu.com/eventful-elections-turkey/):

> Una increíble confusión para 52,9 millones de votantes turcos fue causada por la decisión del gobierno turco de posponer por un día el cambio de hora que se aplica en todo el mundo, cuando los relojes se adelantan una hora. La razón para posponer la aplicación de la hora de verano según el gobierno de Erdogan, fue para facilitar la administración de las elecciones, pero nadie predijo el factor de la "nueva tecnología". Todos los teléfonos inteligentes de los ciudadanos turcos cambiaron la hora automáticamente, resultando en miles de votantes que fueron a a votar más temprano y tuvieron que esperar hasta una hora para poder hacerlo. Problemas similares ocurrieron en computadoras que no habían bajado una nueva versión del software. También hubo problemas en el sistema de despacho de equipajes en el aeropuerto de Estambul ya que el sistema cambió la hora automáticamente, ignorando los planes del gobierno y, como resultado, el equipaje fue enviado a los pasajeros con grandes demoras. También hubo problemas con muchos vuelos ya que los pasajeros confundían el horario de partida.

¿Qué hay con el resto del mundo?
--------------------------------

No sólo Turquía no aprendió de sus propios errores, otros países alrededor del mundo tampoco aprendieron de la experiencia y continúan teniendo este problema. ¿Recuerdan la lista que enumeré antes? Veámosla más de cerca:

*   **Chile** estuvo en "DST permanente" durante 2015, pero el 13 de marzo de 2016, el gobierno anunció que volverían a la hora estándar a partir del 15 de mayo de 2016 **(2 meses de antelación)**.

*   **Rusia** tenía 11 husos horarios diferentes, desde UTC+02 hasta UTC+12, con una historia compleja de cambios en los límites entre ellas.
    
    Para 2016, seis regiones cambiaron sus husos horarios el 27 de marzo de 2016. Cada una de estas regiones tuvo su propia ley para hacer efectivo el cambio. Una fue firmada el 30 de diciembre **(12 semanas de antelación)**, lo cual es razonable. Sin embrgo, las otras fueron firmadas o bien el 15 de febrero **(6 semanas de antelación)** o bien el 9 de marzo **(2 semanas de antelación)**. Otras dos regiones tenían la legislación pendiente durante este período, una de las cuales recién la aprobó el 5 de abril, de la cual la fecha de vigencia se extendió hasta el 24 de abril **(3 semanas de antelación)**. La otra ~todavía está esperando la firma final del Presidente, lo que se espera que ocurra en los próximos días,~ tiene fecha de vigencia al 29 de mayo **(4 semanas de antelación)**. (Actualización: La ley se firmó el 26 de abril).
*   **Venezuela** estuvo en UTC-04:30 desde 2007, pero el gobierno decidió hace poco que retornaría a UTC-04 el 1° de mayo. El cambio se anunció el 15 de abril, el anuncio se convirtió en oficial el 18 de abril al ser publicado en la Gaceta Oficial del país **(2 semanas de antelación)**.

*   **Azerbaiyán** canceló el cambio de hora permanentemente en 2016. La cancelación se haría el 27 de marzo pero recién se anunció el 17 de marzo **(10 días de antelación)**.

*   **Corea del Norte** cambió de UTC-09 a UTC-08:30 el 15 de agosto de 2015. El cambio fue anunciado el 7 de agosto **(8 días de antelación)**.

*   **Haití** canceló el cambio de hora al menos durante el año calendario 2016. Estaba programado para el 13 de marzo, pero el 12 de marzo **(¡sólo 1 día de antelación!)** el gobierno publicó un comunicado de prensa cancelándolo.

Otros problemas con los tiempos
-------------------------------

Mientras todos los cambios descritos conllevan un cierto grado de sorpresa, hay algunas partes del mundo que simplemente no hacen ninguna programación anticipada para el cambio de hora. Fiyi es una de esas zonas. Tuvo DST todos los años desde 2009. Sin embargo, cada año, el gobierno hace un anuncio indicando en qué fecha comienza y termina. Es levemente diferente cada año y no queda claro exactamente cuándo el gobierno tomará la decisión, o qué hacer ante la ausencia de un anuncio. Sería mucho más simple si decidieran hacerlo con una programación regular y sólo hacer anuncios cuando haya desvíos respecto de dicha programación. Otro lugar así es Marruecos, donde la programación del primer inicio y el último fin del DST están definidos adecuadamente, pero cada año, desde 2012 hay un "período de suspensión del DST", de modo que DST termine antes del comienzo de ramadán y se restaure en algún momento luego de la finalización. Esto no sólo significa que los relojes deben cambiarse cuatro veces por año calendario, si no también que nadie sabe bien cuándo son las dos transiciones del medio hasta que el gobierno hace un anuncio. Parte de la razón de esto es que las fechas de ramadán están basadas en las fases observadas de la luna. Sin embargo, mi opinión personal es que aún así deberían fijar las transiciones de DST a un calendario prefijado, aun si comienza antes de ramadán y termina algún tiempo después. La imprevisibilidad de las fechas hace que sea demasiado difícil saber qué hora es en Marruecos a menos que estés realmente allí. (De hecho, Egipto también hizo lo mismo, pero sólo en 2010 y 2014).

Recomendaciones a los gobiernos del mundo
-----------------------------------------

Primero, debo enfatizar que estas son mis recomendaciones personales. No hablo en nombre mi gobierno, de mi empleador, o de la comunidad TZ. Estas recomendaciones están basadas en años de experiencia trabajando con husos horarios en computación, y en la observación de hechos reales. Si vas a hacer cambios en tu(s) huso(s) horario(s), ya sea para la distancia de tu hora estándar desde UTC, o la puesta en funcionamiento o desactivación del cambio de hora para el ahorro de energía, o para las fechas en que los cambios de hora ocurren, entonces, por favor, hacé todo lo siguiente:

1.  Da un aviso con una antelación importante, preferiblemente no menos de 6 meses. Un año o más sería aún mejor.
2.  Proveé ese aviso a través de un decreto oficial de gobierno o una ley. Publicá la ley y disponibilizala a través de un sitio web oficial del gobierno.
3.  Asegurate de incluir los detalles precisos del cambio, incluyendo la fecha y la hora del día en que el mismo debe hacerse efectivo. Por ejemplo, decí "los relojes avanzarán 30 minutos el 1° de abril a la 01:00 hora local". No digas simplemente "la hora va a cambiar en abril". Además, si el cambio sólo afecta una región particular de tu país, por favor, especificá las áreas exactas que son afectadas.
4.  Notificá a tus ciudadanos a través de comunicados de prensa y los medios de noticias, pero no cuentes sólo con esto para comunicar el cambio. El decreto o ley oficial debería estar por encima de cualquier declaración hecha a la prensa.
5.  Enviá notificaciones a la comunidad TZ. Para hacer esto, sólo tenés que mandar un mail a [tz@iana.org](mailto:tz@iana.org) que es la dirección de la [lista de discusión tz](http://www.iana.org/time-zones). El mail debería contener un URL para el anuncio publicado en un sitio web oficial del gobierno.
6.  Si se aborta la decisión de realizar el cambio, por favor da aviso de esto también con mucha anticipación.

Seguir estos lineamientos te asegura que tu cambio sea observado por la tecnología, incluyendo computadoras, teléfonos celulares y otros dispositivos.

Recomendaciones para desarrolladores de software
------------------------------------------------

1.  No trates de inventar tu propio sistema de husos horarios ni pongas una configuración de zonas manualmente en tu aplicación.
2.  Utilizá los recursos de tu plataforma o biblioteca de desarrollo para hacer conversiones de husos horarios. No intentes codificar las reglas vos mismo.
3.  No te bases únicamente en diferencias fijas desde UTC, ni hagas ninguna suposición sobre el cambio de hora para el ahorro de energía de día (_daylight saving time_) para un huso horario en particular.
4.  Estate al tanto de las actualizaciones de los husos horarios. Asegurate de saber como mantenerlos actualizados utilizando los mecanismos de tu plataforma o biblioteca.
5.  Suscribite a la [lista de correo de anuncios de TZ](http://www.iana.org/time-zones), así sabés cuando está disponible cada actulización de los datos.
6.  Si sabés de un cambio que está por ocurrir en un huso horario en un área en particular que difiere de la información conocida actualmente, o si tenés otras preguntas acerca del husos horarios en computación, unite a la [lista de correo electrónico de discusión de TZ](http://www.iana.org/time-zones).
7.  Usá [timeanddate.com](http://timeanddate.com/) para validar cualquier suposición que tengas acerca de los husos horarios para una región en particular. La precisión de este sitio en particular ha sido bien establecida y sus propietarios participan en la comunidad TZ.
8.  Para Windows, .NET y otros productos de Microsoft, seguí el canal de noticias de [este sitio](https://support.microsoft.com/gp/cp_dst) para saber cuándo están disponibles las actualizaciones de la plataforma. (Aunque deberías preferir los husos horarios de IANA cuando sea posible, aun si implica que tenés que utilizar una biblioteca para hacerlo).

Addendum personal
-----------------

Esto lo escribo [yo](/about), [Mariano Absatz](https://twitter.com/el_baby) y **_no_** [Matt Johnson](https://twitter.com/mj1856), con lo cual, las críticas y quejas a esta sección deberán dirigirse directamente a mí. Pienso que si Matt hubiese escrito esta nota a fines de 2008 el mayor ejemplo de torpezas cometidas, habría sido la Argentina en lugar de Turquía, ya que los cambios que se hicieron tanto en el verano 2007/2008 como los que **_no_** se hicieron en octubre de 2008 son un muestrario de todos los errores posibles de ser cometidos. Para información al respecto ver las notas que escribí en ese entonces:

*   [¿Qué hora es?](/que-hora-es)
*   [Llamado a la solidaridad](/llamado-a-la-solidaridad)
*   [Discutiendo sobre el cambio de hora](/discutiendo-sobre-el-cambio-de-hora)
