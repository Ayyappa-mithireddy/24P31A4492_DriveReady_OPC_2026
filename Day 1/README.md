# Day 1 — LLMs & First API Call

## 🎯 Objective
Understand how to interact with Large Language Models (LLMs) using an API, configure a model with LangChain, and experiment with prompts, temperature, memory, and token usage.

## 🧪 Project: Sweet Crumbs AI Bakery Assistant
Built a simple AI assistant for **Sweet Crumbs Home Bakery** using Groq API and LangChain.

### Tech Stack
- Python
- LangChain
- Groq API
- Google Colab

### Model
`openai/gpt-oss-120b`

---

## 📚 What I Learned

- Connecting an LLM using an API
- Installing and using `langchain_groq`
- Securely accessing API keys through Google Colab Secrets
- Using system prompts to control AI behavior
- Controlling creativity using temperature
- Understanding the importance of providing factual context
- Handling unknown questions without hallucinating
- Passing conversation history to maintain context
- Comparing token usage between English and Telugu prompts

---

## 🛠️ Experiments

### 1. First API Call
Connected to Groq using LangChain's `ChatGroq` and initialized the model.

### 2. System Prompts
Created a bakery assistant with predefined business information, including cake prices, ordering requirements, and eggless options.

### 3. Temperature Experiment
Compared model responses using different temperature values:
- `0` — more consistent responses
- `0.2` — slightly varied responses
- `1.2` — more creative and diverse responses

### 4. Hallucination Control
Tested how the model responds when business information is missing from the system prompt.

Added rules to prevent invented prices and delivery promises, and instructed the AI to respond with *"I'll check with the owner."* when it doesn't know.

### 5. Conversation Memory
Tested the difference between individual API calls and passing previous messages as conversation history to help the model remember context.

### 6. Token Usage
Compared input token usage for English and Telugu prompts to observe differences in tokenization across languages.

---

## 🍰 Bakery Assistant Rules

- All cakes are baked after receiving orders.
- Orders require 24 hours' notice.
- Eggless versions are available for all cakes.
- Plum cake — ₹500
- Chocolate cake — ₹650
- Cupcake — ₹80
- Never promise delivery times.
- Never invent prices or business information.

---

## 💡 Key Takeaways

- LLMs need context and instructions to provide reliable responses.
- System prompts help define an AI's role, behavior, and limitations.
- Temperature affects response variability and creativity.
- Conversation history can provide context across multiple API calls.
- API keys must be handled securely.
- Token consumption can vary between languages.

---

## 📂 Files

- `Sweet_Crumbs_Day1.ipynb` — notebook containing API setup, experiments, and implementation.

---

## 🚀 Outcome

Successfully connected to an LLM through an API and built a basic AI bakery assistant while experimenting with prompt engineering, temperature, conversation context, and token usage.
