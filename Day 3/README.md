# Day 3 — LLM Evaluation, Reliability & Agents

## 🎯 Objective
Improve the Sweet Crumbs AI Bakery Assistant by evaluating its responses, testing prompt reliability, implementing deterministic business logic, and exploring LangChain agents.

## 🧪 Project: Sweet Crumbs AI Bakery Assistant

Developed and tested an LLM-powered bakery assistant using LangChain and Groq, with a focus on consistency, correctness, and controlled responses.

### Tech Stack
- Python
- LangChain
- LangChain Groq
- Groq API
- Google Colab
- CSV
- Pandas

### Model
`openai/gpt-oss-20b`

---

## 📚 What I Learned

- Building LLM chains using `ChatPromptTemplate`
- Using `MessagesPlaceholder` for conversation history
- Maintaining conversational memory
- Evaluating LLM responses using test cases
- Measuring pass rates and test scores
- Comparing model behavior at different temperature settings
- Implementing deterministic Python business logic
- Validating input values and handling errors
- Exploring LangChain agents using `create_agent`
- Generating, reading, and exporting CSV files

---

## 🛠️ Experiments & Implementation

### 1. LLM Setup
Configured the Groq API and initialized `ChatGroq` with the `openai/gpt-oss-20b` model using a temperature of `0.3`.

### 2. Prompt Templates & Conversation History
Created a reusable chat prompt with:
- System instructions
- Conversation history
- User questions

Built an `ask()` function to invoke the chain and store previous user and AI messages for contextual conversations.

### 3. Conversation Memory
Tested whether the assistant could remember information from previous messages, such as a customer's name and preferences, across multiple interactions.

### 4. Automated Response Evaluation
Created a set of test cases containing customer questions and expected keywords.

Implemented `run_tests()` to:
- Load test cases from CSV
- Send questions to the LLM
- Check whether responses contain expected keywords
- Mark each test as PASS or FAIL
- Calculate the final score and pass rate

### 5. Temperature Experiment
Compared responses using a higher temperature setting of `1.0`.

Ran the test suite twice to observe how response variability affects correctness and reliability.

- Temperature `0.3` — controlled responses
- Temperature `1.0` — more variation and creativity

### 6. Python Business Logic
Implemented deterministic functions independent of the LLM.

**`get_price()`**
- Calculates the total price based on item and quantity
- Normalizes item names
- Rejects unknown menu items
- Validates that quantities are positive

**`check_order_notice()`**
- Checks whether an order satisfies the 24-hour advance-notice requirement

### 7. Edge Case Testing
Tested valid and invalid inputs, including:
- Different letter cases in item names
- Unknown products
- Zero quantity
- Negative quantity
- Different advance-notice durations

### 8. LangChain Agent Experiment
Created a LangChain agent using `create_agent` and tested its responses to bakery-related questions.

Explored agent behavior for:
- Eggless cake availability
- Price calculations
- Delivery-related questions
- Unknown menu items

### 9. Prompt Improvement & Re-evaluation
Reconstructed the prompt chain with updated system instructions and reran the evaluation suite to observe its behavior.

### 10. CSV Dataset Management
Generated `tests.csv` using Python's CSV module, loaded it with Pandas, examined its columns and records, and exported it from Google Colab.

---

## 🍰 Bakery Business Rules

| Item / Rule | Details |
|---|---|
| Plum Cake | ₹500 |
| Chocolate Cake | ₹650 |
| Cupcake | ₹80 |
| Order notice | Minimum 24 hours |
| Eggless options | Available for all cakes |
| Unknown information | "I'll check with the owner." |
| Delivery | Never promise a time or place |

---

## 💡 Key Takeaways

- LLM responses should be evaluated rather than assumed to be correct.
- Keyword-based test cases provide a simple way to measure response reliability.
- Temperature can affect the consistency of model outputs.
- Python functions are better suited for exact calculations and validation.
- Edge-case testing helps identify weaknesses in application logic.
- Prompt improvement and repeated evaluation are important for reliable AI applications.
- Agents introduce another way to structure LLM-driven applications.

---

## 📂 Files

- `Sweet_Crumbs_Day3.ipynb` — notebook containing LLM setup, prompt chains, automated evaluation, temperature experiments, business logic, and agent experiments.
- `tests.csv` — dataset of bakery questions and expected keywords used to evaluate assistant responses.

---

## 🚀 Outcome

Built a tested AI bakery assistant with conversational memory, automated response evaluation, temperature comparison, validated Python business functions, and initial LangChain agent experimentation.
