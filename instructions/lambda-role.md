# Configurando tu primer Rol para Lambda

Si estás leyendo esta página, probablemente estás configurando tu primer rol para una función Lambda. Aunque es un proceso sencillo, queremos asegurarnos de que entiendas todos los pasos que forman parte de este proceso.

1.  **Elige "Crear un rol personalizado" desde el menú desplegable de Roles de ejecución.**  Esto lanzará una nueva pestaña en tu navegador, así que asegúrate que las ventanas emergentes están habilitadas cuando intentes hacer esto.

    ![](https://i.imgur.com/s8jQwp6.jpg)

2.  **Estás creando un nuevo rol IAM.**  IAM significa Identity and Access Management o Gestión de Accesos e Identidad.  ([Puedes leer más acerca de IAM aquí.](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/introduction.html))  Al crear este rol, estás permitiendo que tu función Lambda sea capaz de crear registros Amazon CloudWatch para tu función.  ([Puedes leer más sobre la gestión de permisos con roles IAM aquí.](https://docs.aws.amazon.com/es_es/lambda/latest/dg/intro-permission-model.html))

3.  **No necesitas hacer ningún cambio.  Haz clic en el botón Permitir situado en la parte inferior derecha.**

    ![](https://i.imgur.com/NCaYtQt.png)

4.  **Esto debería cerrar la nueva pestaña, y completar la información que necesita tu función Lambda.** Si tu sección "Rol de ejecución" no tiene el aspecto de la captura de pantalla que se muestra a continuación, intenta refrescar la página y selecciona el nuevo rol del desplegable "Rol existente".

    ![](https://i.imgur.com/BwIBiHc.png)

5.  **Puedes volver con lo que estabas haciendo.**
