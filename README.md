# Telegram Bot Integrated with Gemini API

This repository contains a Python-based Telegram bot that interacts with the Gemini API (Generative AI by Google) to provide users with AI-generated responses based on their input. The bot uses the Telegram Bot API and integrates it with the Gemini API to generate content dynamically.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Bot Commands](#bot-commands)
- [Error Handling](#error-handling)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Dynamic AI Responses**: The bot interacts with the Gemini API to generate and deliver AI-driven responses to users' messages.
- **Command Handling**: The bot supports commands to initiate interaction.
- **Error Handling**: Graceful error handling to notify users of any issues during interaction.
- **Logging**: Logs information and errors to help in debugging and monitoring the bot's performance.

## Requirements

- Python 3.7 or higher
- A Telegram bot token from [BotFather](https://core.telegram.org/bots#botfather)
- A Gemini API key (You can obtain it from Google's Generative AI services)
- The following Python libraries:
  - `python-telegram-bot`
  - `google-generativeai`

## Installation

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/your-username/telegram-gemini-bot.git
    cd telegram-gemini-bot
    ```

2. **Create a Virtual Environment** *(Optional but recommended)*:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install the Required Packages**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Set Up Your API Keys**:
   - Replace the placeholders in the code with your actual API keys:
     - `TOKEN = 'Enter your telegram bot Token'`
     - `genai.configure(api_key="Enter Your Gemini Key")`

## Usage

1. **Run the Bot**:
   - To start the bot, run the following command in your terminal:
     ```bash
     python bot.py
     ```
   - The bot will start polling for messages and respond to user inputs using the Gemini API.

2. **Interact with the Bot**:
   - Open your Telegram app, search for your bot using its username, and start interacting with it by sending messages.

## Bot Commands

- `/start`: Initiates a conversation with the bot. The bot will greet the user and inform them that they can ask anything.

## Error Handling

- **Logging**: All events and errors are logged using Python's logging module. This helps in identifying issues if the bot fails to respond correctly.
- **User Notification**: If an error occurs during the interaction with the Gemini API, the bot will notify the user with a generic error message, while the detailed error will be logged.

## Customization

You can customize the bot by adding more commands or modifying the existing ones. For example, you can add new command handlers or integrate additional APIs to enhance the bot's functionality.

### Adding a New Command

To add a new command, follow these steps:

1. Define a new function in the bot script:
   ```python
   async def new_command(update: Update, context: ContextTypes.DEFAULT_TYPE):
       await update.message.reply_text("This is a new command!")
   ```

2. Register the new command handler:
   ```python
   application.add_handler(CommandHandler("newcommand", new_command))
   ```

3. Run the bot again, and you can now use `/newcommand` in the chat.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request. Please ensure that your code adheres to the existing coding style and passes all tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

*Note*: Replace the placeholders in the code (`Enter Your Gemini Key` and `Enter your telegram bot Token`) with your actual keys before running the bot. Never share your API keys publicly, and store them securely.

