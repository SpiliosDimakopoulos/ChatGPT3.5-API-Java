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

## Known Limitations

1. **Single Message Handling**: The application currently processes one message at a time. Multi-turn conversations are not supported.
2. **Basic Error Feedback**: Errors from the API (e.g., invalid input or quota exceeded) are not detailed in the logs.
3. **Synchronous Operation**: While thread-safe, the application relies on synchronized methods and waits for the response, which can lead to blocking behavior.
4. **Limited Logging**: Minimal logging is implemented, making debugging and performance monitoring more challenging.
5. **File Dependency**: The application depends on `Config.txt` for the API key. If this file is missing or corrupted, the program cannot run.

---

## Technical Notes

### Security
- Storing the API key in a plain-text file (`Config.txt`) is not ideal for production environments. Consider using secure vaults or encrypted storage for sensitive credentials.

### Compatibility
- Tested on JDK 8 and later versions. Ensure your development environment supports the required Java libraries (`java.io`, `java.net`, and `java.nio.charset`).

### API Rate Limits
- The OpenAI API has rate limits based on your subscription tier. Frequent API calls may lead to throttling or errors.

---

## Troubleshooting

### Common Issues and Fixes

- **`FileNotFoundException` for `Config.txt`:**
  - Ensure the file is placed in the `lib` directory.
  - Verify the correct file path if running the application from a different working directory.

- **`HTTP request failed with response code`:**
  - Check the validity of the API key in `Config.txt`.
  - Verify that your API key has sufficient credits and is active.

- **No Response or Empty Output:**
  - Confirm that the message passed to the `SendGPT` object is not empty or null.
  - Check internet connectivity and the API endpoint URL.

---

## Contribution Guidelines

We welcome contributions to improve **SendGPT**. Here’s how you can contribute:

1. **Fork the Repository**: Start by creating a fork of this project.
2. **Submit Changes**: Create a new branch, make your changes, and submit a pull request.
3. **Testing**: Ensure your changes pass all tests and do not break existing functionality.
4. **Documentation**: Update this README if your contribution adds or changes functionality.

---
