# Build and deploy your own ChatGPT AI app to help you code!
# Use npm install cors dotenv nodemon openai in the folder "server" and npm install in the folder "client" using node version 16 or higher.
# Use npm run server to run server.js and npm run dev to run script.js, you need run both at the same time if you will use this local.
# If you are going to use this, you need to change the API key in the .env for the API key provided by OpenAI.
# Thank you! <3

# =====EXPLICACION DEL CODIGO CHATBOT.JS=============

# La primera línea importa dos archivos SVG (Scalable Vector Graphics) que se utilizan como iconos del usuario y del bot.
# Luego, el código selecciona el elemento de formulario y el contenedor de chat en el DOM (Document Object Model) utilizando la función querySelector.
# La función loader muestra una animación de "cargando" en el elemento especificado. La animación consiste en añadir un punto cada 300   milisegundos hasta que se han añadido cuatro puntos, y luego volver a empezar.
# La función typeText muestra el texto especificado en el elemento especificado de manera efecto tipográfico, agregando un carácter cada 20 milisegundos.
# La función generateUniqueId genera un ID único para cada elemento de mensaje del bot. Esto se utiliza para aplicar el efecto tipográfico a la respuesta del bot de manera independiente de cualquier otro mensaje.
# La función chatStripe genera un elemento de chat para el usuario o el bot con el mensaje especificado. Utiliza los iconos del usuario y del bot importados al principio del archivo.
# La función handleSubmit es el controlador del evento submit del formulario. En primer lugar, se crea una instancia de FormData a partir del formulario y se envía al servidor a través de una solicitud POST. Luego, se muestra un elemento de chat para el mensaje del usuario y un elemento de chat en blanco para la respuesta del bot. Después de eso, se muestra una animación de "cargando" en el elemento de chat del bot y se envía una solicitud POST al servidor para obtener la respuesta del bot. Cuando se recibe la respuesta, se elimina la animación de "cargando" y se muestra el texto de la respuesta del bot con el efecto tipográfico.
# Finalmente, el código agrega dos controladores de eventos al formulario: uno para el evento submit y otro para el evento keyup. El controlador #del evento submit llama a la función handleSubmit, mientras que el controlador del evento keyup llama a la función handleSubmit solo si la #tecla presionada es "Enter".

# =====EXPLICACION DEL CODIGO SERVER.JS=============
# La primera línea importa la librería de express, que se utiliza para crear el servidor.
# La segunda línea importa todas las exportaciones de la librería dotenv, que se utiliza para cargar variables de entorno desde un archivo .env.
# La tercera línea importa la librería cors, que se utiliza para habilitar la solicitud entre orígenes (CORS).
# La cuarta línea importa las clases Configuration y OpenAIApi de la librería openai.
# Luego, se cargan las variables de entorno del archivo .env con dotenv.config().
# A continuación, se crea una instancia de Configuration con la clave de API de OpenAI, que se obtiene de una variable de entorno. Después, se crea una instancia de OpenAIApi con la configuración anterior.
# A continuación, se crea una aplicación de express y se configura para utilizar cors y para aceptar solicitudes JSON. 
# Se define un controlador de ruta para la ruta raíz que envía un mensaje de bienvenida.
# Se define otro controlador de ruta para la ruta raíz que recibe un mensaje del usuario y envía una solicitud a OpenAI para obtener una respuesta del bot. Si la solicitud se procesa correctamente, se envía la respuesta del bot al cliente; de lo contrario, se envía un error al cliente.
# Finalmente, se inicia el servidor en el puerto 5000 y se muestra un mensaje en la consola para indicar que el servidor se ha iniciado.