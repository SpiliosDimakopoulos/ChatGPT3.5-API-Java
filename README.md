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

