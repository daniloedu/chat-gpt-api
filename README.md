# OpenAI Assistant for Jupyter Notebooks.

## Introduction

This repository contains a Jupyter notebook facilitating interaction with OpenAI's GPT-3.5 Turbo model. The notebook allows users to send various prompts to the model and receive responses in the style specified. It also provides tools to manage and monitor token usage for API calls.

## Requirements

### Prerequisites

1. **Python Environment:** The code is written in Python and requires a Python 3.x environment.
2. **Python Libraries:** Ensure you have the following libraries installed:
  - `os`
  - `openai`
  - `tiktoken`
  - `dotenv`
3. **OpenAI API Key:** You'll need an API key from OpenAI to interact with the service. Store it securely in an `.env` file or another secure location and make sure it's accessible to the notebook.

## Code Explanation

### Setup and Initialization
- **Library Imports:** The necessary Python libraries for the code's operation are imported.
- **Environment Variable Loading:** The code uses `dotenv` to load essential environment variables, particularly the OpenAI API key.

### Function Defitions
1.`get_completion(prompt, model="gpt-3.5-turbo")`: This function sends a prompt to the specified model and returns its response. It sets up the message format required by the OpenAI ChatCompletion API.
2. `get_completion_from_messages(messages, model="gpt-3.5-turbo", temperature=0, max_tokens=500)`: A more flexible function that allows sending multiple messages to the model, including system-level instructions. The function supports adjusting the randomness (`temperature`) and the maximum response length (`max_tokens`).
3. `get_completion_and_token_count(messages, model="gpt-3.5-turbo", temperature=0, max_tokens=500)`: This function not only gets the model's response but also returns the token usage for the API call, allowing users to monitor their usage.

## Demonstrations and Examples
The notebook contains several examples showcasing how to use the functions. These examples include:
  - Basic question-answer interactions.
  - Getting responses in the style of Dr. Seuss.
  - Restricting response lengths.
  - Combining multiple instructions.
  - Monitoring token usage for API calls.

## Usage Tips

- Ensure you're mindful of token usage, especially when dealing with larger prompts or allowing larger maximum tokens.
- Adjust the temperature parameter if you wish to have more deterministic or more random responses from the model.
- When using system-level instructions (like asking the model to respond in the style of Dr. Seuss), ensure the message format is correct and the role is set to 'system'.
