# Day 2 — Prompt Engineering & Building Smarter LLM Applications

## 🎯 Objective
Explore how prompt engineering improves LLM behavior and build a bakery assistant that can classify customer messages, extract structured order details, maintain conversation context, and handle pricing using Python.

## 🧪 Project: Sweet Crumbs AI Bakery Assistant

Enhanced the Day 1 bakery assistant by experimenting with different prompting techniques and integrating LLM responses with Python logic.

### Tech Stack
- Python
- LangChain
- Groq API
- Google Colab
- JSON

### Model
`openai/gpt-oss-120b`

---

## 📚 What I Learned

- Writing effective system prompts
- Comparing prompts with and without behavioral rules
- Few-shot prompting using examples
- Customer message classification
- Extracting structured information from natural language
- Parsing LLM-generated JSON using Python
- Maintaining conversation history and memory
- Limiting conversation context using recent turns
- Using Python functions to calculate prices
- Combining LLMs with traditional Python logic

---

## 🛠️ Experiments & Implementation

### 1. Prompt Engineering — Without Rules vs With Rules
Compared model responses with and without explicit rules to understand how instructions affect behavior.

Added constraints to prevent the AI from:
- Promising delivery times
- Inventing unavailable information
- Making unsupported claims

### 2. Few-Shot Prompting
Provided examples to teach the model how to classify customer messages into:

- `ORDER` — Placing, modifying, or cancelling an order
- `PRICE` — Asking about prices or payment
- `DELIVERY` — Asking about delivery or pickup
- `OTHER` — General questions

### 3. Customer Message Classification
Tested the classifier against different customer queries involving orders, prices, delivery, eggless cakes, cancellations, and decorations.

### 4. Structured Data Extraction
Extracted order details from natural-language messages into JSON:

- Customer name
- Item
- Quantity
- Order date
- Eggless preference

Handled missing information using `null` and validated the response using Python's `json` module.

### 5. Conversation Memory
Maintained conversation history by storing user and AI messages in a list and passing that history back to the LLM.

Tested whether the assistant could remember a customer's name and order details across multiple messages.

### 6. Context Window Management
Experimented with limiting conversation history to recent turns using `MAX_TURNS` and `recent_history`.

### 7. Python-Based Pricing System
Created a menu dictionary and a `get_price()` function to calculate order totals based on the item and quantity.

This keeps pricing calculations deterministic rather than relying on the LLM to perform arithmetic.

### 8. Integrated Bakery Assistant
Combined business facts, menu prices, system instructions, and conversational context into a more structured customer support assistant.

---

## 🍰 Bakery Menu

| Item | Price |
|---|---:|
| Plum Cake | ₹500 |
| Chocolate Cake | ₹650 |
| Cupcake | ₹80 |

### Bakery Rules
- Cakes are baked after receiving orders.
- Orders require 24 hours' notice.
- Eggless versions are available for all cakes.
- Never promise delivery times.
- Never invent prices or services.
- Unknown information → *"I'll check with the owner."*

---

## 💡 Key Takeaways

- Specific instructions make LLM responses more controlled and reliable.
- Few-shot prompting helps guide outputs using examples.
- LLMs can convert unstructured text into structured JSON.
- Conversation history enables contextual responses.
- Context management helps control how much conversation is sent to a model.
- Python is better suited for deterministic calculations such as pricing.
- Combining LLM reasoning with traditional code makes applications more practical.

---

## 📂 Files

- `Sweet_Crumbs_Day2.ipynb` — notebook containing prompting experiments, classification, extraction, memory, and pricing implementation.

---

## 🚀 Outcome

Built a more capable AI bakery assistant by combining prompt engineering, few-shot classification, JSON-based information extraction, conversational memory, and Python-based business logic.
