# NovaAI - Intelligent Hybrid Chatbot 🧠✨

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

An advanced conversational AI that intelligently blends a generative language model (**Microsoft DialoGPT-large**) with a retrieval-augmented generation (**RAG**) system to deliver natural, context-aware, and factually grounded conversations.

**GitHub Repository:** [https://github.com/singhsuhas77/NovaAI.git](https://github.com/singhsuhas77/NovaAI.git)

---
## 📖 Table of Contents
- [About The Project](#about-the-project)
- [Key Features](#-key-features)
- [Architecture](#-architecture)
- [Technologies Used](#-technologies-used)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#-usage)
- [Testing & Performance](#-testing--performance)
- [Future Work](#-future-work)
- [Conclusion](#-conclusion)
- [Contact](#-contact)

---
## 📍 About The Project

[cite_start]Traditional chatbots often struggle with disjointed conversations, a lack of factual grounding, and poor user engagement[cite: 557, 558, 571]. [cite_start]They either follow rigid rules or, if purely generative, risk producing nonsensical or "hallucinated" responses[cite: 562, 563].

[cite_start]**NovaAI** addresses these limitations by implementing a **hybrid architecture**[cite: 334]. [cite_start]It combines the creative, human-like conversational power of **DialoGPT** with the factual accuracy of a **Sentence-BERT + FAISS** retrieval system[cite: 324]. This ensures that conversations are not only engaging and coherent but also factually accurate and reliable.

[cite_start]The system is enhanced with real-time utilities like date/time lookups, mathematical calculations, and a Wikipedia search function, making it a versatile and intelligent AI assistant[cite: 336].

---
## ✨ Key Features

* [cite_start]**Hybrid Conversational Engine:** Blends generative AI (DialoGPT) for fluency with a retrieval system (RAG) for factual accuracy[cite: 614, 615].
* [cite_start]**Context-Aware Dialogue:** Maintains conversation history using a sliding-window memory to ensure coherent, multi-turn dialogues[cite: 611, 612].
* [cite_start]**Knowledge Retrieval:** Integrates seamlessly with the **Wikipedia API** to answer factual questions like "who is..." or "what is..."[cite: 621].
* **Real-Time Utilities:**
    * [cite_start]Provides the current **time** and **date**[cite: 620].
    * [cite_start]Performs **mathematical calculations**[cite: 622].
    * [cite_start]Tells a variety of randomized **jokes** to improve user engagement[cite: 628].
* [cite_start]**High Performance:** Optimized for low latency (<1.5s response time) with GPU acceleration support[cite: 634, 676].
* [cite_start]**Scalable & Modular:** Built with a clean, extensible framework that allows for easy integration of new skills and knowledge sources[cite: 638, 642].

---
## 🏗️ Architecture

NovaAI processes user input through a multi-layered pipeline:
1.  **Command Check:** The input is first checked for specific utility commands (e.g., `time`, `date`, `calculate`, `joke`).
2.  **Knowledge Query:** If not a command, it's analyzed for knowledge-based questions (e.g., "who is..."). [cite_start]If detected, the query is routed to the **Wikipedia API** for a concise summary[cite: 220, 221].
3.  **Generative Response:** For general conversation, the input is passed to the **DialoGPT-large** model. [cite_start]The prompt is enriched with the recent conversation history to maintain context[cite: 231].
4.  [cite_start]**Factual Grounding:** The RAG system, using **Sentence-BERT** embeddings and a **FAISS** vector index, provides factual grounding to guide the generative process and reduce inaccuracies[cite: 124, 165, 166].

---
## 🛠️ Technologies Used

* **Core AI & NLP:**
    * [cite_start]**Hugging Face Transformers:** For the `DialoGPT-large` model[cite: 51, 52, 721].
    * [cite_start]**Sentence-Transformers:** For the `all-MiniLM-L6-v2` embedding model[cite: 53, 54, 728, 730].
    * [cite_start]**PyTorch:** As the backend for model inference and tensor operations[cite: 70, 749].
    * [cite_start]**FAISS (Facebook AI Similarity Search):** For efficient and fast vector similarity search in the knowledge base[cite: 63, 742].
* **Knowledge & Utilities:**
    * [cite_start]**Wikipedia API:** For fetching factual summaries[cite: 59, 734].
    * [cite_start]**DateTime & Pytz:** For timezone-aware time and date functions[cite: 80, 761].
    * [cite_start]**Regex:** For input sanitization and expression parsing[cite: 82, 766].
* **Development & Deployment:**
    * [cite_start]**Python 3.8+**[cite: 90, 777].
    * [cite_start]**Jupyter Notebook:** For prototyping and debugging[cite: 97, 781].
    * [cite_start]**Git & GitHub:** For version control[cite: 104, 789].
    * [cite_start]**Docker:** (Planned) For containerization and easy deployment[cite: 100, 785].

---
## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

Make sure you have Python 3.8 or higher installed. You will also need `pip` for installing packages.

### Installation

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/singhsuhas77/NovaAI.git](https://github.com/singhsuhas77/NovaAI.git)
    cd NovaAI
    ```

2.  **Install the required packages:**
    ```sh
    pip install transformers torch sentence-transformers faiss-cpu wikipedia datetime pytz
    ```
    *Note: Use `faiss-gpu` instead of `faiss-cpu` if you have a compatible NVIDIA GPU with CUDA installed for better performance.*

---
## 💬 Usage

To start the chatbot, run the main Python script. The application will launch an interactive command-line interface (CLI).

```python
# In your main script or a Jupyter cell
from nova_ai_module import NovaAI # Assuming your class is in this module

# Initialize the chatbot
nova = NovaAI()

# Add initial knowledge (optional)
nova.add_to_knowledge_base("The Eiffel Tower is in Paris")
nova.add_to_knowledge_base("Python is a programming language")

# Start the chat session
nova.chat()
