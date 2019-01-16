# Construye un Skill de Hola Mundo para Alexa con el SDK de ASK para Python
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[Interfaz Vocal de Usuario (VUI)](./1-voice-user-interface.md) - [Función Lambda](./2-lambda-function.md) - [Conectar la VUI al Código](./3-connect-vui-to-code.md) - [**Pruebas**](./4-testing.md) - [Próximos pasos](./5-next-steps.md)

## Probando tu skill de Alexa

Hasta ahora, hemos [creado una Interfaz Vocal de Usuario](./1-voice-user-interface.md) y [una función Lambda](./2-lambda-function.md), y [las hemos interconectado](./3-connect-vui-to-code.md).  Tu skill está listo para probarlo.

1.  **Volvamos al portal [Amazon Developer Portal](https://developer.amazon.com/edw/home.html#/skills/list) y selecciona el skill de la lista.** Podrías tener aún el portal en una pestaña abierta del navegador si has seguido este tutorial desde el principio.

2. Abre el panel de pruebas haciendo clic en el enlace **Test** situado en el menú de navegación superior.

3. Habilita las pruebas seleccionando **Development** en el menú desplegable situado junto al texto **Test is disabled for this skill,** que inicialmente está configurado con el valor **Off**.

4. Para validar que tu skill funciona como esperas, invoca tu skill desde el **Alexa Simulator**. Puedes escribir los mensajes que quieres enviar o hacer clic y mantener pulsado el icono del micrófono, que aparece en la caja de texto, para utilizar tu propia voz.
	1. **Escribe** "Abre" seguido del nombre de invocación que has dado a tu skill en el [Paso 1](./1-voice-user-interface.md). Por ejemplo, "Abre saludador".
	2. **Usa tu voz** haciendo clic sobre el icono del micrófono y manteniéndolo pulsado dí "Abre" seguido del nombre de invocación que le has dado a tu skill.
	3. **Si has olvidado el nombre de invocación** de tu skill, ve el panel **Build** ubicado en el menú de navegación superior y selecciona Invocation para conocer el nombre.

5. Asegúrate que tu skill funciona de la forma en la que lo has diseñado.
	* Después de que interactúes con Alexa Simulator, deberías ver que las cajas **JSON Input** (la petición) y **JSON Output** (la respuesta) dentro de Skill I/O se llenan con datos JSON. Puedes ver también el **Device Log** para tener más información de tus pasos.
	* Si tu skill no funciona como esperabas, puedes investigar el contenido JSON para ver exáctamente qué está enviando y recibiendo Alexa desde nuestro endpoint. Si algo se rompe, AWS Lambda ofrece una herramienta adicional de pruebas para ver qué puede ir mal con tu skill.

6.  **Configura un evento de prueba en AWS Lambda.** Ahora que te has familiarizado con las cajas de **JSON Input (petición)** y **JSON Output (respuesta)** en el Alexa Simulator, es importante que sepas que puedes usar tus **peticiones** para probar directamente tu función Lambda cada vez que la actualices. Para hacer esto:
    1.  Introduce un utterance (declaración) en el simulador del servicio, y copia el contenido JSON que se encuentra dentro de la caja **JSON Input** y que constituye la petición Lambda generada. Usaremos el contenido JSON para el siguiente paso.

    2.  **Abre tu función Lambda en AWS, abre el menú "Selec. evento de prueba" y selecciona "Configurar eventos de prueba."**

        <img src="https://i.imgur.com/rbQcics.png" />

    3.  **Selecciona "Crear un evento de prueba nuevo". Elige del menú desplegable "Alexa Start Session" como plantilla de eventos.** Puedes elegir cualquier evento de prueba de la lista, puesto que son únicamente plantillas de peticiones de eventos, pero "Alexa Start Session" es una plantilla fácil de recordar.

        <img src="https://i.imgur.com/PjclPKq.png" />

    4.  **Escribe un nombre dentro de la caja de diálogo Nombre del evento. Borra el contenido del editor de código, y pega en el editor la petición Lambda que copiaste previamente.** El Nombre del evento sólo es visible para tí. Nombra tu evento de prueba con algo descriptivo y que te sirva para recordarlo. Para nuestro ejemplo, hemos introducido un nombre de evento "startSession". La ventaja de copiar y pegar tu petición Lambda desde el Alexa Simulator es que puedes probar diferentes utterances y eventos del skill que amplíen las plantillas preconfiguradas de Lambda.

        <img src="https://i.imgur.com/9kZaC9d.png" />

    5.  **Haz clic en el botón "Crear".** Esto guardará tu evento de prueba y te devolverá a la configuración principal de tu función Lambda.

    6.  **Haz clic en el botón "Probar" para ejecutar el evento de prueba "startSession".**

        <img src="https://i.imgur.com/iRlIQ2w.png" />

        Esto te proporciona visibilidad de cuatro elementos:

        *  **Tu respuesta, que aparecerá listada bajo "Execution Result."**

           <img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/fact/4-5-5-1-execution-result._TTH_.png" />

        *  **Un resumen de las estadísticas de tu petición.** Esto incluye cosas como la duración, los recursos y la memoria utilizados.

           <img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/4-5-5-2-summary._TTH_.png" />

        *  **Salida del Log.**  Empleando sentencias print() o del logger de Python en tu código Lambda, puedes analizar qué está pasando en el interior de tu función, y ayudarte a comprender qué ocurre cuando algo va mal.  Encontrarás que el log proporciona una información muy valiosa según vayas creando skills más avanzados.

           <img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/4-5-5-3-log-output._TTH_.png"/>

        *  **Un enlace a tus logs de [CloudWatch](https://console.aws.amazon.com/cloudwatch/home?region=eu-west-1#logs:) para esta función.**  Esto te mostrará **todas** las respuestas y logs de la interacción con cada usuario.  Esto es muy útil, especialmente cuando estás probando tu skill desde un dispositivo con tu voz. (Es el enlace "[Click here](https://console.aws.amazon.com/cloudwatch/home?region=es-west-1#logs:)" que aparece en la descripción de la sección Log Output.)

7.  **Otros métodos de prueba que puedes considerar:**

    *  [Echosim.io](https://echosim.io) - una herramienta de pruebas de skills de Alexa, usando un navegador, que facilita la realización de tus pruebas sin necesidad de transportar un dispositivo físico allí donde vayas.
    *  [Pruebas de Unidad con Alexa](https://github.com/alexa/alexa-cookbook/tree/master/testing/postman/README.md) - un acercamiento moderno a la realización de pruebas de unidad con tus skills de Alexa usando [Postman](http://getpostman.com) y [Amazon API Gateway](https://aws.amazon.com/es/api-gateway/).

8.  **Si tu skill de ejemplo está funcionando correctamente, puedes personalizar tu skill.**.

[Continuar el tutorial](5-next-steps.md)
----
