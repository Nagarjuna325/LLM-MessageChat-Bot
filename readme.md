
# 🧠 Memory-Enabled Multilingual Chatbot using LangChain & Groq

This project demonstrates how to build an intelligent chatbot with memory capabilities using LangChain, powered by the Groq LLM (`Gemma2-9b-It`). It includes multilingual support, message trimming for long conversations, and conversation history via session management.

---

## 📁 File Overview

- `1-chatbots.ipynb` – Main notebook containing all the logic for:
  - Connecting to Groq API
  - Maintaining chat history
  - Using prompt templates
  - Supporting multiple languages
  - Trimming chat history to fit within token limits

---

## ⚙️ Setup Instructions

### 1. Clone the repository


git clone https://github.com/your-username/langchain-groq-chatbot.git
cd langchain-groq-chatbot
2. Create a virtual environment

python -m venv venv
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate
3. Install dependencies

pip install -r requirements.txt
4. Set up your .env file
Create a .env file in the root directory and add your Groq API key:

GROQ_API_KEY=your_groq_api_key_here
🚀 Running the Notebook
To run the chatbot:

jupyter notebook
Open 1-chatbots.ipynb and run cells step-by-step.

💬 Features
✅ Memory across sessions using RunnableWithMessageHistory

✅ Dynamic prompt templating with system messages

✅ Language-aware responses (e.g., English, Hindi)

✅ Token-aware message trimming via trim_messages

✅ Powered by Groq’s Gemma2-9b-It model

🌐 Example

HumanMessage(content="Hi, my name is Arjun")
# Later...
HumanMessage(content="What's my name?")
The assistant will remember that your name is Arjun if you're using the same session.

You can also specify response language:

{
  "messages": [HumanMessage(content="Hi")],
  "language": "Hindi"
}
📦 Dependencies
Make sure these packages are included in requirements.txt:

langchain
langchain-core
langchain-groq
langchain-community
python-dotenv
tqdm
🧠 Notes on History Management
To avoid overflowing the LLM's context window:

Message history is trimmed using trim_messages

Only the last few tokens are retained based on a limit (max_tokens=45)

You can control inclusion of system messages and trimming strategy
