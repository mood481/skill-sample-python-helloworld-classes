# Construye un Skill de Hola Mundo para Alexa con el SDK de ASK para Python
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Interfaz Vocal de Usuario (VUI)](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/1-locked._TTH_.png)](./1-voice-user-interface.md)[![Función Lambda](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/2-locked._TTH_.png)](./2-lambda-function.md)[![Conectar la VUI al Código](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/3-on._TTH_.png)](./3-connect-vui-to-code.md)[![Pruebas](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/4-off._TTH_.png)](./4-testing.md)[![Próximos pasos](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/5-off._TTH_.png)](./5-next-steps.md)

## Conectando tu Interfaz Vocal de Usuario con tu Función Lambda

En la [página #1](./1-voice-user-interface.md) de esta guía, creamos una interfaz vocal de usuario para los intents y utterances (declaraciones) que esperamos de los usuarios. En la [página #2](./2-lambda-function.md), creamos una función Lambda que contiene toda la lógica para el skill.  En esta página, necesitaremos conectar estas dos piezas juntas.

1.  **Volvamos al portal [Amazon Developer Portal](https://developer.amazon.com/edw/home.html#/skills/list) y selecciona el skill de la lista.** Podrías tener aún el portal en una pestaña abierta del navegador si has seguido este tutorial desde el principio.

2. Selecciona la pestaña **Endpoint** situada en el panel de navegación situado a la izquierda.

3.  **Selecciona la opción "AWS Lambda ARN" para nuestro endpoint.** Tienes la posibilidad de alojar tu código en el lugar que desees, pero para los propósitos de simplicidad y frugalidad, estamos usando AWS Lambda. ([Lee más acerca de cómo alojar tu propio servicio web para tu skill (en Inglés)](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/developing-an-alexa-skill-as-a-web-service).)  Con la capa gratuita de AWS, puedes conseguir 1.000.000 de peticiones gratis por mes y hasta 3,2 millones de segundos de tiempo de cálculo por mes. Lee más en [https://aws.amazon.com/es/free/](https://aws.amazon.com/es/free/).  Además, Amazon ofrece ahora [Créditos promocionales de AWS para desarrolladores que tienen skills de Alexa publicados que pueden suponer costes de explotación en AWS para esos skills](https://developer.amazon.com/alexa-skills-kit/alexa-aws-credits).

4.  Pega el ARN (Nombre de recurso Amazón o Amazon Resource Name) de tu función Lambda en la caja de texto rotulada **Default Region**.

5. Haz clic en el botón **Save Endpoints** en la parte superior del panel principal.

6. **Haz clic en el botón "Next: Testing" para continuar a la página #4 de esta guía.**

 <br/><br/>
<a href="./4-testing.md"><img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/buttons/button_next_testing._TTH_.png" /></a>
