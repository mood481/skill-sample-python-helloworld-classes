Construye un Skill de Hola Mundo para Alexa con el SDK de Python de ASK (utilizando clases)
=========================================

Este tutorial es una traducción al español del [tutorial oficial de Alexa](https://github.com/alexa/skill-sample-python-helloworld-classes) publicado por Amazon, en el que se han traducido las instrucciones del tutorial y los mensajes del skill y en el que se han incluido enlaces a la documentación oficial en español y otros elementos para que puedas aprender e interactuar con el skill en español (es-ES). Todo el código, así como las instrucciones del tutorial, son Copyright 2018 de Amazon.com.

Este tutorial guiará a los desarrolladores primerizos a través de los pasos requeridos para la creación de un skill utilizando esta plantilla de hola mundo. Este tutorial asume que estás familiarizado con Python (o un lenguaje de programación similar) y el kit de Alexa Skills (ASK).

<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

Conceptos
--------

Este ejemplo sencillo no tiene dependencias externas o gestión de sesiones, y muestra el ejemplo más básico de cómo crear una función Lambda para atender las peticiones de un skill de Alexa.

Configuración
-----

Para ejecutar este skill de ejemplo sólo necesitarás dos cosas. La primera es desplegar el código en Lambda, y la segunda es configurar el skill de Alexa para emplear Lambda. Para comenzar puedes hacer clic en el siguiente enlace.

[Comenzar](./instructions/1-voice-user-interface.md)
------

Los skills pueden construirse ya sea implementando las clases ``AbstractRequestHandler``  o usando el decorador ``request_handler`` del Skill Builder. Puede consultarse más información en la [documentación oficial en Inglés](https://alexa-skills-kit-python-sdk.readthedocs.io/en/latest/REQUEST_PROCESSING.html#request-handlers).

Este skill de ejemplo muestra cómo implementar la clase ``AbstractRequestHandler`` y cómo registrar el manejador de clases explícitamente en el objeto Skill Builder.
El código para esta implementación se encuentra dentro de la carpeta [lambda/py](lambda/py).

El mismo ejemplo usando ``decoradores`` se encuentra en el repositorio
[skill-sample-python-helloworld-decorators](https://github.com/alexa/skill-sample-python-helloworld-decorators).

Recursos adicionales
--------------------

### Comunidad

-  [Amazon Developer Forums](https://forums.developer.amazon.com/spaces/165/index.html) : ¡Únete a la conversación!
-  [Hackster.io](https://www.hackster.io/amazon-alexa) - Mira lo que otros están construyendo con Alexa.

### Guías y tutoriales

-  [Guía de Diseño para la Voz](https://developer.amazon.com/designing-for-voice/) -
   Un gran recurso para aprender sobre el diseño de interfaces de usuario orientadas a la voz y a la conversación.

### Documentación

-  [SDK de Python para Alexa Skills Kit](https://pypi.org/project/ask-sdk/)
-  [Documentos oficiales del SDK de Alexa Skills Kit para Python](https://alexa-skills-kit-python-sdk.readthedocs.io/en/latest/)
-  [Documentos oficiales de Alexa Skills Kit](https://developer.amazon.com/docs/ask-overviews/build-skills-with-the-alexa-skills-kit.html)

