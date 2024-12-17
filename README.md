# ReadMe: SendGPT - Java Application for Communicating with OpenAI GPT-3.5 Turbo API

## Overview

**SendGPT** is a Java application designed to send user messages to OpenAI's GPT-3.5 Turbo model and receive AI-generated responses. The application uses HTTP requests to interact with OpenAI's API and provides a synchronized, thread-safe way to handle message exchange.

---

## Features

- **Send Messages**: Allows users to input messages that are processed by GPT-3.5 Turbo.
- **API Response Handling**: Extracts and formats responses from the API in a user-friendly manner.
- **Configurable API Key**: Reads the API key from an external file for security.
- **Thread-Safe Communication**: Ensures that message handling is synchronized.

---

## Prerequisites

1. **Java Development Kit (JDK)**: Version 8 or higher.
2. **API Key**: A valid OpenAI API key.
3. **Configuration File**:
   - Place a file named `Config.txt` in the `lib` directory.
   - Add your OpenAI API key as the first line of this file.

---

## Directory Structure

project/ │ ├── src/ │ └── SendGPT.java ├── lib/ │ └── Config.txt └── README.md

---

## How to Use

### Step 1: Set Up the API Key
1. Create a directory named `lib` in your project folder.
2. Inside `lib`, create a file named `Config.txt`.
3. Paste your OpenAI API key into the first line of the file.

### Step 2: Run the Application
1. Compile the `SendGPT.java` file using `javac SendGPT.java`.
2. Run the program using `java SendGPT`.

---

## Key Methods and Functionality

### `run()`
- Sends a POST request to the OpenAI API with the user-provided message.
- Handles the API response and extracts the generated content.

### `getAPIKEyfromFile()`
- Reads the API key from `Config.txt`.

### `extractContentFromResponse(String response)`
- Parses the JSON response from the API to extract the AI-generated content.

### `waitingForResponse()`
- Pauses the thread until the AI response is received.

---

## Example Usage

1. Create an instance of the `SendGPT` class:
   ```java
   SendGPT sendGPT = new SendGPT("Hello, GPT!");

