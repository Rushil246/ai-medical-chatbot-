# ai-medical-chatbot-

# AI Medical Chatbot

This project is an AI-powered medical chatbot that leverages a large language model (LLM) from HuggingFace, integrated with FAISS for memory retrieval. The chatbot is designed to provide accurate responses based on the given context and user queries.

---

## Features

- **LLM Integration**: Uses the Mistral-7B-Instruct model from HuggingFace.
- **Custom Prompting**: Allows setting custom prompt templates for tailored responses.
- **Memory Retrieval**: Utilizes FAISS for efficient context-based memory retrieval.
- **Streamlit Interface**: Provides a user-friendly interface for interaction.

---

## Prerequisites

1. **Python**: Ensure Python 3.8 or higher is installed.
2. **Pipenv**: Install Pipenv for managing the virtual environment.  
   Follow the official guide: [Install Pipenv Documentation](https://pipenv.pypa.io/en/latest/installation.html)
3. **HuggingFace Token**: Obtain a HuggingFace API token and set it as an environment variable (`HF_TOKEN`).

---

## Setup Instructions

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone <repository-url>
cd ai-medical-chatbot
```

### 2. Install Dependencies
Run the following commands to install the required packages:
```bash
pipenv install langchain langchain_community langchain_huggingface faiss-cpu pypdf
pipenv install huggingface_hub
pipenv install streamlit
```

### 3. Set Environment Variables
Create a `.env` file in the project root and add your HuggingFace token:
```env
HF_TOKEN=your_huggingface_token
```

Alternatively, export the token directly in your terminal:
```bash
export HF_TOKEN=your_huggingface_token  # For Linux/Mac
set HF_TOKEN=your_huggingface_token     # For Windows
```

### 4. Run the Application
Start the chatbot interface using Streamlit:
```bash
pipenv run streamlit run app.py
```

---

## Project Structure

- **`connect_memory_with_llm.py`**: Contains functions to load the LLM, set custom prompts, and connect the LLM with FAISS.
- **`app.py`**: The main Streamlit application for user interaction.
- **`README.md`**: Documentation for setting up and running the project.

---

## Key Functions

### `load_llm(huggingface_repo_id)`
Loads the HuggingFace LLM with the specified repository ID.

### `set_custom_prompt(custom_prompt_template)`
Creates a custom prompt template for the chatbot.

---

## Notes

- Ensure the HuggingFace model repository ID is correctly set in the code (`HUGGINGFACE_REPO_ID`).
- The chatbot is designed to provide responses strictly based on the given context. If the answer is not found in the context, it will respond with "I don't know."

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
