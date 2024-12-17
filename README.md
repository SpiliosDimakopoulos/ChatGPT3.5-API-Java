SendGPT - Java Application for Communicating with OpenAI GPT-3.5 Turbo API
Overview
SendGPT is a Java application designed to send user messages to OpenAI's GPT-3.5 Turbo model and receive AI-generated responses. The application uses HTTP requests to interact with OpenAI's API and provides a synchronized, thread-safe way to handle message exchange.

Features
Send Messages: Allows users to input messages that are processed by GPT-3.5 Turbo.
API Response Handling: Extracts and formats responses from the API in a user-friendly manner.
Configurable API Key: Reads the API key from an external file for security.
Thread-Safe Communication: Ensures that message handling is synchronized.
Prerequisites
Java Development Kit (JDK): Version 8 or higher.
API Key: A valid OpenAI API key.
Configuration File:
Place a file named Config.txt in the lib directory.
Add your OpenAI API key as the first line of this file.
Directory Structure
css
Copy code
project/
│
├── src/
│   └── SendGPT.java
├── lib/
│   └── Config.txt
└── README.md
How to Use
Step 1: Set Up the API Key
Create a directory named lib in your project folder.
Inside lib, create a file named Config.txt.
Paste your OpenAI API key into the first line of the file.
Step 2: Run the Application
Compile the SendGPT.java file using javac SendGPT.java.
Run the program using java SendGPT.
Key Methods and Functionality
run()
Sends a POST request to the OpenAI API with the user-provided message.
Handles the API response and extracts the generated content.
getAPIKEyfromFile()
Reads the API key from Config.txt.
extractContentFromResponse(String response)
Parses the JSON response from the API to extract the AI-generated content.
waitingForResponse()
Pauses the thread until the AI response is received.
Example Usage
Create an instance of the SendGPT class:
java
Copy code
SendGPT sendGPT = new SendGPT("Hello, GPT!");
Start the API request:
java
Copy code
sendGPT.run();
Wait for the response:
java
Copy code
sendGPT.waitingForResponse();
Retrieve and display the response:
java
Copy code
System.out.println("AI Response: " + SendGPT.retResponse);
Error Handling
FileNotFoundException: Triggered if Config.txt is missing.
IOException: Captures other input/output-related issues.
HTTP Errors: Throws an exception if the API request fails (e.g., incorrect API key or invalid input).
Notes
The API key should remain confidential. Avoid hardcoding it in the source code.
Ensure that your OpenAI API key has sufficient quota to handle requests.
Dependencies
Java's built-in libraries (java.io, java.net, java.nio.charset).
Future Improvements
Add support for more complex GPT interactions (e.g., system messages or multi-turn conversations).
Include detailed logging for better debugging and monitoring.
Enhance error handling with more specific feedback for API-related issues
