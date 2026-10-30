# 🔮 SupportPearlz AI — Customer Support Knowledge Assistant

SupportPearlz AI is a Streamlit-based customer-support application prototype for Pearlz Home Systems. It provides a modern workspace where users can ask questions about AquaPearl products and company policies, explore a sample knowledge base, run grounding and safety scenarios, evaluate predefined support cases, and review session-level performance.

The application focuses on providing source-aware customer support. When the assistant finds relevant information in its sample knowledge base, it displays the answer with document references. When the available information does not support an answer, the assistant refuses to guess and recommends contacting a human support representative.

> **Project Status:** This project currently contains an interactive UI prototype with a local, rule-based response engine and a four-document sample knowledge base. Live OpenAI responses, semantic/vector retrieval, real document ingestion, and persistent database storage are not connected yet.

---

## ✨ Features

### 1. Modern Support Dashboard
- Professional dark teal and mint color theme.
- Gradient background and subtle grid effects.
- Glassmorphism-style cards and interactive buttons.
- Modern typography and support-themed images.
- Sidebar navigation and workspace overview.

### 2. Customer Chat
- Interactive customer-support chat interface.
- Multi-turn conversation history.
- Quick-question buttons for common customer requests.
- Rule-based answers for supported product and policy topics.
- Source references for supported answers.
- Refusal mechanism for unsupported questions.
- Helpful / Not Helpful feedback buttons.
- Export conversations as Markdown files.

### 3. Knowledge Base Explorer
- Displays four sample knowledge-base documents.
- Search documents by title, text, and section.
- Filter documents by type (Manual or Policy).
- View document details and content.
- Download the knowledge base as a CSV file.

### 4. Grounding & Safety Audit
- Prompt injection testing.
- Unanswerable question testing.
- False warranty premise testing.
- Product troubleshooting scenarios.
- Source verification and refusal behavior.

### 5. Evaluation Harness
- Predefined customer-support test cases.
- Automated local rule-based evaluation.
- PASS/FAIL test results.
- Overall evaluation pass rate.
- Downloadable evaluation results.

### 6. Performance Dashboard
- Total customer questions.
- Source-backed response count.
- Refusal and human handoff count.
- Average local response-processing time.
- Question activity by support topic.
- Downloadable session analytics.

---

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application logic |
| Streamlit | Interactive web application |
| Pandas | Data management and analytics |
| python-dotenv | Environment variable management |
| HTML | Application structure and styling |
| CSS | Custom UI design and visual effects |

---

## 📁 Project Structure

```text
SupportPearlz-AI/
│
├── SupportPearlz_AI_Pro.py
│   └── Main Streamlit application
│
├── README.md
│   └── Project documentation
│
├── requirements.txt
│   └── Python dependencies
│
└── .env
    └── Optional environment variables (keep private)
```

---

## ⚙️ Installation and Setup

### Step 1: Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
```

Open the project folder:

```bash
cd YOUR-REPOSITORY
```

Replace the repository URL with your actual GitHub repository URL.

### Step 2: Create a Virtual Environment

For Windows:

```bash
python -m venv venv
```

Activate the environment:

```bash
venv\Scripts\activate
```

For macOS/Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Required Packages

Run:

```bash
pip install streamlit pandas python-dotenv
```

Alternatively, create a `requirements.txt` file:

```text
streamlit
pandas
python-dotenv
```

Then install the dependencies:

```bash
pip install -r requirements.txt
```

### Step 4: Run the Application

Execute the following command in your VS Code terminal:

```bash
streamlit run SupportPearlz_AI_Pro.py
```

The application will open in your browser.

Default local URL:

```text
http://localhost:8501
```

---

## 🚀 How to Use

1. Run the application using Streamlit.
2. Enter an OpenAI API key in the initial access screen to unlock the workspace.
3. Navigate through the application using the sidebar.
4. Open Customer Chat to ask questions about Pearlz products and policies.
5. Use quick-question buttons to test common customer queries.
6. Explore the Knowledge Base to search and view available documents.
7. Open Grounding & Safety Audit to test refusal and security scenarios.
8. Run the Evaluation Harness to check predefined test cases.
9. Visit Performance to analyze session-level support activity.
10. Export conversations, knowledge-base records, and evaluation results when required.

### Example Customer Questions

```text
My AquaPearl purifier beeps three times. What should I do?

What does the warranty cover?

How long does delivery take to Skardu?

Can I return an opened purifier?

Do you offer student discounts?
```

---

## 📚 Sample Knowledge Base

The application contains four sample documents:

| Document | Type | Information |
|---|---|---|
| AquaPearl 500 Pro Manual | Manual | Error E-03, three beeps, and filter reset instructions |
| Warranty Policy §3.2 | Policy | Warranty coverage and filter cartridge exclusions |
| Shipping Policy | Policy | Skardu delivery timelines and next-day delivery cities |
| Refund & Returns Policy | Policy | 14-day return window and return conditions |

These documents are currently defined inside the Python application.

---

## 🔄 Application Workflow

The application follows this basic customer-support workflow:

```text
        Customer Question
                |
                v
       Question Processing
                |
                v
      Local Rule-Based Matching
                |
                v
       Sample Knowledge Base
                |
          +-----+-----+
          |           |
          v           v
    Information    No Supporting
       Found         Information
          |           |
          v           v
    Generate       Refuse to Guess
    Response       Human Handoff
          |           |
          +-----+-----+
                |
                v
       Display Response
                |
                v
       Show Source Reference
                |
                v
       Update Session Analytics
```

---

## 🔐 API Key and Security

- The initial access screen checks whether the entered key starts with `sk-` and meets the minimum length requirement.
- This is only basic format validation, not actual OpenAI API authentication.
- The current application does not send customer questions to OpenAI.
- API keys should never be hard-coded into Python source files.
- Never upload private API keys or `.env` files to GitHub.
- Use environment variables or Streamlit secrets for future deployment.
- Implement proper authentication and API verification before production use.

---

## ⚠️ Current Project Limitations

The current version is an interactive prototype.

The following components are not fully connected yet:

- Live OpenAI API integration.
- Real AI-generated customer-support responses.
- Semantic search and vector database.
- PDF and external document ingestion.
- Document chunking and embedding generation.
- Actual hybrid search and reranking.
- Automated LLM-based hallucination detection.
- Persistent database storage.
- Real API token and cost tracking.

The current chatbot uses keyword-based rules and a small sample knowledge base. The evaluation and safety tests also operate on this local rule-based engine.

The application stores chat history, feedback, and analytics in Streamlit session state, so this information is not permanently saved.

---

## 🛠️ Future Improvements

The following enhancements are planned for future development:

1. Integrate the OpenAI API for live AI-powered responses.
2. Add PDF and document upload functionality.
3. Implement document extraction and text preprocessing.
4. Add document chunking and embedding generation.
5. Connect a vector database for semantic search.
6. Implement hybrid retrieval and reranking.
7. Generate grounded answers with source citations.
8. Improve prompt injection and hallucination detection.
9. Add persistent database storage for conversations and documents.
10. Implement real-time token usage and API cost tracking.
11. Add user authentication and role-based access control.

---

## 🤝 Contributing

Contributions and suggestions are welcome.

To contribute:

1. Fork the repository.
2. Create a new feature branch:

```bash
git checkout -b feature/your-feature
```

3. Make your changes.
4. Commit your changes:

```bash
git add .
git commit -m "Add your feature"
```

5. Push your branch:

```bash
git push origin feature/your-feature
```

6. Open a Pull Request.

---

## 📄 License

No license has been specified for this project yet. Before publishing it as an open-source project, select an appropriate license and add a `LICENSE` file to the repository.

---

## 💎 Project Information

**Project Name:** SupportPearlz AI

**Project Type:** AI-Based Customer Support Knowledge Assistant

**Application Framework:** Streamlit

**Programming Language:** Python

**Domain:** Artificial Intelligence / Customer Support / Knowledge Management

---

**SupportPearlz AI — Customer care that is clear, grounded, and human-centered.**
