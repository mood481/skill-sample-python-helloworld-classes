# Construye un Skill de Hola Mundo para Alexa con el SDK de ASK para Python
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Interfaz Vocal de Usuario (VUI)](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/1-locked._TTH_.png)](./1-voice-user-interface.md)[![Función Lambda](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/2-on._TTH_.png)](./2-lambda-function.md)[![Conectar la VUI al Código](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/3-off._TTH_.png)](./3-connect-vui-to-code.md)[![Pruebas](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/4-off._TTH_.png)](./4-testing.md)[![Próximos pasos](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/5-off._TTH_.png)](./5-next-steps.md)

## Configurando una función Lambda usando Amazon Web Services

En el [primer paso de esta guía](1-voice-user-interface.md), creamos la interfaz vocal de usuario (VUI) para nuestro skill de Alexa.  En esta página, crearemos una función Lambda usando [Amazon Web Services](http://aws.amazon.com).  Puedes [leer más sobre qué es una función Lambda](https://aws.amazon.com/es/lambda/), pero para el propósito de esta guía, lo que necesitas saber es que Lambda es donde vive nuestro código.  Cuando un usuario pide a Alexa que use nuestro skill, es nuestra función Lambda la que interpreta la interacción apropiada, y proporciona los elementos de conversación de vuelta al usuario.

1.  **Ve a http://aws.amazon.com e inicia sesión en la consola.** Si aún no tienes una cuenta, necesitarás crear una. [Visita esta guía rápida de configuración de una nueva cuenta AWS (en Inglés)](https://github.com/alexa/alexa-cookbook/blob/master/guides/aws-security-and-setup/set-up-aws.md).

    [![Iniciar sesión](https://i.imgur.com/q1kDpx8.png)](https://console.aws.amazon.com/console/home)

2.  **Elige "Services" en la parte superior de la pantalla y escribe "Lambda" en la caja de búsqueda.**  Puedes también encontrarla en la lista de servicios.  Está en la sección "Compute".

    [![Lambda](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-2-services-lambda._TTH_.png)](https://console.aws.amazon.com/lambda/home)

3.  **Comprueba tu región AWS.** Lambda solo funciona con el Kit de Alexa Skills en cuatro regiones: US East (N. Virginia), EU (Ireland), US West (Oregon) y Asia Pacific (Tokyo).  Asegúrate de que eliges la región más cercana a tus clientes.

    ![Regiones lambda](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-3-check-region._TTH_.png)

4.  **Haz clic en el botón "Crear una función".** Debería estar cerca de la parte superior de la pantalla.

    ![Crear función](https://i.imgur.com/hjMvbf2.png)

5.  **Haz clic en "Crear desde cero".**  Configuraremos nuestra función Lambda a continuación.
    1. Estos valores únicamente serán visibles para tí, pero asegúrate de que das un nombre significativo a tu función. "ejemploPythonHolaMundo" será suficiente si no tienes otra idea para un nombre.

    2. Del menú desplegable "Tiempo de ejecución" selecciona la versión de Python que soporta tu sistema.  Este tutorial, y el código de ejemplo, funcionan ya sea con Python 2.7 o 3.6. Para comprobar la versión de Python, intenta usar el siguiente comando en un terminal.
        ```
        $ python --version
        Python 2.7.10
        ```

    3. **Configura un rol para tu función Lambda.**  Si no has hecho esto anteriormente, tenemos una [guía detallada para configurar tu primer rol para Lambda (Inglés)](https://github.com/alexa/alexa-cookbook/blob/master/guides/aws-security-and-setup/lambda-role.md).  Si ya lo has hecho anteriormente, solo necesitarás seleccionar un rol en el desplegable **Rol existente**.

    4. Haz click en **Crear una función**.

6.  **Configura tu desencadenador.** Existen muchos servicios AWS diferentes que pueden desencadenar la ejecución de una función Lambda, pero para el propósito de esta guía, necesitamos seleccionar "Alexa Skills Kit" desde las opciones situadas a nuestra izquierda.

    Una vez que hayas seleccionado Alexa Skills Kit, desplázate hacia abajo y encuentra la sección de Verificación del ID de habilidad (skill). Aunque querrás pegar tu ID de skill en el campo ID de habilidad, de momento y para este tutorial, haz clic en Deshabilitar.  Haz clic en el botón **Añadir** situado en la parte inferior derecha.  Haz clic en el botón naranja **Guardar** situado en la esquina superior derecha.

7.  **Finaliza la configuración de tu función**. Haz clic en el nombre de tu función (lo encontrarás en el medio de la pantalla) y desplázate hasta el final de la página, verás un editor de código Cloud9.

    Hemos preparado el código para este skill [aquí](../lambda/py). Para subir el código correctamente a Lambda, necesitarás hacer lo siguiente:

    1. Este skill usa el [SDK de ASK para Python](https://github.com/alexa/alexa-skills-kit-sdk-for-python) para el desarrollo. El código del skill se proporciona en el fichero [hola_mundo.py](../lambda/py/hola_mundo.py), y las dependencias se encuentran en el fichero [requirements.txt](../lambda/py/requirements.txt). Descarga los contenidos de la carpeta [lambda/py](../lambda/py).
    2. En tu sistema, navega hasta la carpeta lambda e instala las dependencias en una nueva carpeta llamada “skill_env” usando el siguiente comando:

        ```
        pip install -r py/requirements.txt -t skill_env
        ```

    3. Copia los contenidos de la carpeta `lambda/py` en la carpeta `skill_env`.

        ```
        cp -r py/* skill_env/
        ```

    4. Comprime con zip los contenidos de la carpeta `skill_env`. Recuerda hacer un zip con los **contenidos** de la carpeta y **NO** la carpeta en sí misma.
    5. Desde la consola AWS Lambda, cambia el desplegable **Tipo de entrada de código** a **Cargar un archivo .zip** y sube el fichero zip creado en el paso previo.
    6. Cambia el nombre del controlador a ``hola_mundo.handler`` y haz clic en **Guardar**.

    *(Opcional)* Sigue la documentación de [Introducción](https://alexa-skills-kit-python-sdk.readthedocs.io/en/latest/GETTING_STARTED.html#adding-the-ask-sdk-for-python-to-your-project) del SDK de ASK para Python, para conocer formas alternativas de instalar el SDK y cómo desplegarlo en la consola AWS Lambda.

8. (Opcional) Haz clic en el menú desplegable **Configurar eventos de prueba** situado en la parte superior de la página.

    1. Selecciona 'Amazon Alexa Start Session' del menú desplegable 'Plantilla de eventos'.
    2. Escribe `LaunchRequest` en el campo 'Nombre del evento'.
    3. Haz clic en el botón naranja 'Crear' situado en la parte inferior de la página.
    4. Haz clic en el botón **Probar** situado en la parte superior de la página.
    5. Deberías ver una caja color verde claro con el mensaje: *Execution result: succeeded* en la parte superior de la página.

9. **Como paso final, copia el valor ARN ubicado en la esquina superior derecha.** Necesitarás este valor en la próxima sección de esta guía. Para continuar haz clic en el siguiente botón.

[![Next Step](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/buttons/button_next_connect_vui_to_code._TTH_.png)](3-connect-vui-to-code.md)
