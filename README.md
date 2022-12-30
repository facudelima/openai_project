# Build and deploy your own ChatGPT AI app to help you code!
Use npm install cors dotenv nodemon openai in the "server" folder and npm install in the "client" folder using node version 16 or higher.
Use npm run server to run server.js and npm run dev to run script.js, you need to run both at the same time if you are going to use this locally.
If you are going to use this, you need to change the API key in the .env file for the API key provided by OpenAI.
# Thank you! <3

# =============EXPLANATION OF THE CHATBOT.JS CODE=============

~ The first line imports two Scalable Vector Graphics (SVG) files that are used as icons for the user and the bot.
~ Then, the code selects the form element and the chat container in the Document Object Model (DOM) using the querySelector function.
~ The loader function displays a "loading" animation on the specified element. The animation consists of adding a dot every 300 milliseconds until four dots have been added, and then starting over.
~ The typeText function displays the specified text in the specified element with a typographic effect, adding one character every 20 milliseconds.
~ The generateUniqueId function generates a unique ID for each bot message element. This is used to apply the typographic effect to the bot's response independently of any other message.
~ The chatStripe function generates a chat element for the user or the bot with the specified message. It uses the user and bot icons imported at the beginning of the file.
~ The handleSubmit function is the event handler for the form's submit event. First, a FormData instance is created from the form and sent to the server via a POST request. Then, a chat element is displayed for the user's message and a blank chat element for the bot's response. After that, a "loading" animation is displayed on the bot's chat element and a POST request is sent to the server to get the bot's response. When the response is received, the "loading" animation is removed and the text of the bot's response is displayed with the typographic effect.
~ Finally, the code adds two event handlers to the form: one for the submit event and one for the keyup event. The submit event handler calls the handleSubmit function, while the keyup event handler calls the handleSubmit function only if the pressed key is "Enter".

# =============EXPLANATION OF THE SERVER.JS CODE=============
~ The first line imports the express library, which is used to create the server.
~ The second line imports all exports from the dotenv library, which is used to load environment variables from a .env file.
~ The third line imports the cors library, which is used to enable cross-origin request (CORS).
~ The fourth line imports the Configuration and OpenAIApi classes from the openai library.
~ Then, the environment variables from the .env file are loaded with dotenv.config().
~ Next, a Configuration instance is created with the OpenAI API key, which is obtained from an environment variable. Then, an OpenAIApi instance is created with the previous configuration.
~ Next, an express app is created and configured to use cors and to accept JSON requests.
~ A route handler is defined for the root route that sends a welcome message.
~ A route handler is defined for the /chat route that handles POST requests. First, the request body is extracted and a chat request is created using the OpenAIApi instance. Then, the chat request is sent to the OpenAI API and the response is sent back to the client.
~ Finally, the server is set to listen on the port specified in the PORT environment variable.