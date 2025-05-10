# NovaAI

NovaAI is an interactive conversational AI assistant powered by state-of-the-art machine learning models like **DialoGPT** for generating responses and **SentenceTransformer** for semantic search. It is designed to hold contextual conversations, retrieve information from Wikipedia, tell jokes, fetch date and time, perform basic arithmetic, and more.

## Features

* Conversational AI with memory of previous interactions
* Real-time date and time fetching
* Wikipedia summary retrieval
* Joke generation
* Basic calculator functions
* Interactive chatbot experience

## Installation

To run NovaAI, ensure you have the following packages installed:

```bash
pip install transformers torch sentence-transformers faiss-cpu wikipedia datetime pytz
```

## Usage

Run the notebook and initialize the chatbot:

```python
from NovaAI import NovaAI
nova = NovaAI()
nova.start_chat()
```

### Commands Supported:

* **General Questions**: Just ask anything, and NovaAI will try to answer.
* **Time:** `What time is it?`
* **Date:** `What's the date today?`
* **Weather:** `How's the weather?`
* **Jokes:** `Tell me a joke.`
* **Wikipedia Lookup:** `Who is Albert Einstein?` or `What is Quantum Physics?`
* **Math Calculations:** `5 + 3`, `12 * 4`

To quit the chat, simply type:

```
quit
```

## Project Structure

* `NovaAI`: Main class that handles chatbot operations
* `retrieve_knowledge`: Searches for predefined information
* `generate_response`: Generates AI responses based on context
* `start_chat`: Launches the interactive chat loop

## Future Enhancements

* Integration with real-time weather API
* Enhanced memory capabilities
* Support for voice input and output

## Contributions

Contributions are welcome! Please follow the guidelines for pull requests.

## License

This project is licensed under the MIT License.
