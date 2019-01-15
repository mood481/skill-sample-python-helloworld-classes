# Construye un Skill de Hola Mundo para Alexa con el SDK de ASK para Python
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Interfaz Vocal de Usuario (VUI)](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/1-on._TTH_.png)](./1-voice-user-interface.md)[![Función Lambda](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/2-off._TTH_.png)](./2-lambda-function.md)[![Conectar la VUI al Código](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/3-off._TTH_.png)](./3-connect-vui-to-code.md)[![Pruebas](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/4-off._TTH_.png)](./4-testing.md)[![Próximos pasos](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/5-off._TTH_.png)](./5-next-steps.md)

## Configurando tu Skill de Alexa en la consola del Desarrollador

1.  **Ve a la [Alexa Developer Console](https://developer.amazon.com/es/alexa?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=quiz-game-python-V2_GUI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_quiz-game-python-V2_GUI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs).  En la esquina superior derecha de la pantalla, haz clic en el botón "Identificarse".**
(Si aún no tienes una cuenta, podrás crear una nueva gratuitamente.)

2.  Una vez que hayas iniciado la sesión, haz clic en **Mis consolas Alexa** y selecciona **Skills**.

3.  Desde la **Alexa Developer Console** haz clic en el botón **Create Skill**, situado a la derecha sobre tu lista de Skills de Alexa.

4. Da a tu nuevo skill un **Nombre**, por ejemplo, 'Saludador'. Este es el nombre que se mostrará en la tienda de Skills de Alexa, el nombre que emplearán tus usuarios.

5. Selecciona el idioma por defecto.  Este tutorial asume que has seleccionado 'Spanish (ES)' para usar español como idioma por defecto.

6. Selecciona el modelo **Custom** en la sección *'Choose a model to add to your skill'*. Haz clic en el botón **Create Skill** situado en la parte superior derecha. Se creará un nuevo skill y podremos comenzar a trabajar con él.

7. **Construye el modelo de interacción de tu skill**
	1. En el panel de navegación situado a la izquierda de la pantalla, selecciona la pestaña **JSON Editor** que se encuentra bajo **Interaction Model**. En el campo de texto que se proporciona, reemplaza el código existente con el [contenido del fichero](../models/es-ES.json) proporcionado para el [Modelo de Interacción](../models/es-ES.json).  Haz clic sobre el botón **Save Model**.
    2. Si quieres cambiar el nombre de invocación del skill, selecciona la pestaña **Invocation**. Introduce un nuevo nombre para el campo **Skill Invocation Name**. Este el nombre que tus usuarios necesitarán decir para iniciar el skill. En este caso, se ha preconfigurado para que sea 'saludador'.
    3. Haz clic en el botón "Build Model" para construir tu modelo de interacción.

	**Nota:**  Notarás que las pestañas **Intents** y **Slot Types** se llenarán automáticamente con los datos almacenados en el fichero JSON que contiene el modelo de interación que acabas de aplicar a tu skill. Siéntete libre de explorar los cambios y para aprender más sobre **Intents**, **Slots**, y **Utterances** abre nuestra [documentación técnica en una nueva pestaña](https://developer.amazon.com/es/docs/custom-skills/create-intents-utterances-and-slots.html?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=quiz-game-python-V2_GUI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_quiz-game-python-V2_GUI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs).

8. **Opcional:** Selecciona un intent expandiendo el contenido de la pestaña **Intents** situada en el panel de navegación situado a la izquierda. Añade más declaraciones (utterances) de ejemplo para los intents generados recientemente. Piensa en todas las formas diferentes en las que un usuario podría solicitar que tuviera lugar un intent. Se proporcionan unos pocos ejemplos. Asegúrate de hacer clic en **Save Model** y **Build Model** después de hacer cambios en la pestaña Intents.

9. Si tienes éxito al construir tu modelo de interacción, continúa con el siguiente paso haciendo clic en el botón **Next: Lambda Function**. Si no, deberías ver un error. Intenta resolver los errores. En el siguiente paso de esta guía, crearemos una función Lambda en la consola de desarrollador de AWS, pero mantén esta página del navegador abierta, porque volveremos a ella en [Página #3: Conectar la VUI con el Código](./3-connect-vui-to-code.md).

     Si tienes un error en el modelo de interacción, comprueba las sugerencias de la siguiente lista:

     *  **¿Copiaste y pegaste correctamente el código proporcionado?**
     *  **¿Añadiste por accidente algún carácter al modelo de interacción?**

[![Siguiente](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/buttons/button_next_lambda_function._TTH_.png)](./2-lambda-function.md)
