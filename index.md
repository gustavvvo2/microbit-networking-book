Prefacio
========

![Cover image](introduction/cover.png)

Acerca del libro
------------------------------------

Este libro presenta una serie de actividades para conocer aspectos básicos sobre redes de ordenadores usando placas micro:bit. Aunque no aprenderás todos los aspectos de las redes, esperamos que sirva como un buen punto de partida.

Para que las micro:bits puedan comunicarse usaremos la comunicación de radio a radio. Al escuchar la palabra radio solemos pensar en nuestras emisoras musicales favoritas, pero una radio, un trasceptor de radio (transmisor/receptor) se usa en las comunicaciones para generar y recibir ondas de radio que pueden contener información como audio, vídeo o datos digitales. Y todas las micro:bit llevan una radio incorada [^1].

Cada capítulo presenta retos interesantes sobre las comunicaciones usando micro:bits. Cada pocos capítulos se intercala un juego que pone en práctica todo lo aprendido. Para programar las placas se usa el editor de bloques de JavaScript, [Microsoft Makecode](https://makecode.microbit.org/)[^2]. 

Al escribir el libro no se ha asumido conocimiento previo alguno sobre comunicaciones o redes. 

Sin embargo, sí se asume que has escrito algunos programas sencillos con una micro:bit. Por ejemplo, se espera que entiendas lo que es una variable, una instrucción si-entonces-sino o un bucle. Pero si no tienes mucha experiencia programando, tampoco te preocupes, porque los programas con que trabajaremos son muy sencillos y tendrás oportunidad de practicar en cada capítulo.

Hay que tener en cuenta que esta obra que estás leyendo es un traducción al castellano que, aunque respeta en general la obra original, ha sido modificada, resumida o ampliada en diferentes capítulos por el autor de la adaptación.


Ediciones
---------

Es posible descargar una versión PDF del libro original en inglés: [descarga](https://microbit.nominetresearch.uk/networking-book-pdf/networking_with_the_microbit.pdf).

También se pueden comprar copias impresasen [Amazon.co.uk](https://www.amazon.co.uk/Networking-micro-bit-Anthony-Kirby/dp/1973396769) o [Amazon.com](https://www.amazon.com/Networking-micro-bit-Anthony-Kirby/dp/1973396769). 

Cuando finalice la traducción al español se generará una edición en PDF y se incluirá también para descarga.



Sobre los autores
-----------------

Los autores de la obra original son investigadores, lo que significa que tratan de encontrar nuevas ideas y productos. Su empresa Nominet se encarga de la parte de internet que controla como se usan los nombres (como
[http://www.bbc.co.uk)](http://www.bbc.co.uk)) cuando la gente, los ordenadores y otros dispositivos se conectan a otros ordenadores a través de internet. 

Comprender cómo hablan los ordenadores entre sí es algo importante, y es por eso que escribieron este libro. Anthony & Cigdem disfrutaron realmente al diseñar los retos y los desafíos del libro, y esperan que tú también lo hagas al tratar de resolverlos.

El autor de esta traducción al español y adaptación es [Jesús Moreno León](http://jemole.me/), profesor de informática en Sevilla (España). Las modificaciones que se han realizado de la obra original se deben a que Jesús está utilizando estas prácticas en sus clases, por lo que algunos capítulos se han adaptado a las necesidades concretas de su alumnado.


Resumen
-------

- [**Conexión de micro:bits por cables**](wiredcommunication/wiredcommunication.md)  
    Este capítulo es una introducción y una demostración divertida de las redes de ordenadores. Las placas micro:bit se pueden comunicar al conectarse mediante cables. Y a través de estos enviars imágenes entre micro:bits.

- [**Comunicación broadcast: de una a todas**](broadcast/broadcast.md)  
    Comenzars a utilizar la comunicación por radio y aprenderás acerca de la comunicación broadast. Así, una micro:bit enviará información a todas las demás micro:bits de la clase. Pero, ojo, si todas las placas hacen lo mismo es como si todos hablésemos al mismo tiempo.

- [**Comunicación por grupos: de una a muchas**](groupcommunication/groupcommunication.md)
    Formaremos grupos pequeño para enviar y recibir información de un número limitado de micro:bits. Esto es más manejable que broadcast. El reto está en elegir un identificador que sea único para tu grupo.

- [**Juego 1: Corazones agitados**](shakeydonkey/shakeydonkey.md)
    Este juego usa la radio de la micro:bit. Tras programarlo siguiendo las instrucciones, jugarás varias partidas, entenderás el código e, incluso, tratarás de hackearlo para poder ganar siempre.

- [**Comunicación unicast: de una a una**](unicast/unicast.md)
    Las comunicaciones broadcast y multicast son divertidas. Pero a veces solo quieres hablar con una persona determinada. Esto se llama comunicación unicast. Para ello, descubriremos que es necesario que cada micro:bit tenga un identificador único.

- [**Two-way Unicast**](twowayunicast/twowayunicast.md)
    It’s no use talking with somebody if you don’t get a response back. In this chapter, you will program
    your micro:bit to send a message and to get a reply. Also, you will work out how long it takes for a
    reply to come back. Doing this, you will also program one of the most important tools used in the
    Internet: Ping.

- [**Game 2: Rock-Paper-Scissors over Radio**](rockpaperscissors/rockpaperscissors.md)  
    This is not like the traditional Rock-Paper-Scissors game. It
    works over the radio!

- [**Handling errors: Retransmissions**](retransmissions/retransmissions.md)
     Nothing is perfect, not even radio communication. What happens if
    your message gets lost on the way? In this chapter, you will test
    methods for dealing with message loss. For instance, does it help if
    you send your messages more than once?

- [**Handling errors: Acknowledgements**](acknowledgements/acknowledgements.md)
    It’s a waste to retransmit if the other side already received the message! The receiver needs a
    standard reply (or an acknowledgement) to avoid this. At the sending side, if you do not receive an
    acknowledgement, you can assume that your message wasn’t received. In this chapter, you will test
    how well acknowledgments work to improve reliability.

- [**Game 3: Battleship over Radio**](battleship/battleship.md)
    You have come far. Now you are ready for another classic game!
    You will write a version of the famous Battleship game using
    your micro:bits. Your experience with radio communication and
    networking will help you along the way.

Let’s start!

[^1]: The CPU on the micro:bit is a Nordic Semiconductor nRF51822 and contains a built-in 2.4GHz radio module. This radio can be configured to run Bluetooth Low Energy
(BLE) protocol but in this book, we will use the simpler micro:bit to micro:bit communication.

[^2]: This version of the book uses JavaScript Blocks Editor; we are also working on a MicroPython version.
