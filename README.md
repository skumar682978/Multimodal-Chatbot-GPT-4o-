# Multimodal-Chatbot-GPT-4o-

## Project Summary
This project integrates the OpenAI API with Chainlit to process and respond to various types of messages, including text, images, and audio files. It utilizes environment variables for secure API key management. Here is a detailed explanation:

### Components
1) Environment Setup

 - The dotenv package is used to load environment variables from a .env file, ensuring secure handling of the OpenAI API key.
  
2) OpenAI Client Initialization

 - The OpenAI client is initialized using the API key loaded from the environment variables.
  
3) Message Appending Function (append_messages)

 - This function constructs a list of messages based on the provided image URL, text query, and audio transcript.
 - It sends the compiled messages to the OpenAI GPT-4 model and returns the response.
  
4) Image to Base64 Conversion (image2base64)

 - This function reads an image file and converts it to a base64-encoded string, which is used to embed images in the messages sent to the OpenAI API.
  
5) Audio Processing Function (audio_process)

 - This function processes audio files by transcribing them into text using OpenAI's Whisper model.
  
6) Chat Message Handler (chat)

 - This asynchronous function listens for incoming messages, identifies and processes image and audio files, and prepares a response.
 - It uses the image2base64 function for image files and the audio_process function for audio files.
 - Based on the type of message content (text, image, audio), it calls the append_messages function to generate a response.
 - The response is then sent back through Chainlit's messaging framework.
  
### Workflow

1) Environment Setup

 - Load the OpenAI API key from the .env file.
 
2) Initialization

 - Initialize the OpenAI client with the loaded API key.
  
3) Message Handling

 - For incoming messages, identify if they contain images or audio files.
 - Convert image files to base64 strings if present.
 - Transcribe audio files to text if present.
 - Compile the messages based on the content type.
 - Send the messages to the OpenAI GPT-4 model and retrieve the response.
 - Send the generated response back to the user.
This project showcases a comprehensive integration of the OpenAI API with Chainlit for handling and processing various types of user inputs, providing a flexible and interactive messaging system.
