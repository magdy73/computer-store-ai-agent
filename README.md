# 🖥️ Computer Store AI Agent (n8n Workflow)

## 📌 Overview

This project is an AI-powered automation workflow built using **n8n**.
It acts as a smart assistant for a computer store, handling customer interactions via Telegram, answering inquiries using product data from Google Sheets, and enabling purchase requests by notifying the store owner via email.

---

## ⚙️ System Architecture

The workflow is composed of the following main components:

### 1. Telegram Bot (Entry Point)

* Receives customer messages
* Sends each message to the AI Agent for processing

---

### 2. AI Agent (Core Logic)

* The brain of the system
* Powered by:

  * LLM (Google Gemini)
  * Memory (conversation context)
  * Tools (Google Sheets + Gmail)

#### Responsibilities:

* Understand customer requests
* Respond using product data
* Detect purchase intent
* Ask for customer details (name + phone number) before purchase
* Generate a well-formatted email

---

### 3. Memory (Conversation Context)

* Stores recent conversation history
* Solves the issue of stateless messages
* Important for:

  * Maintaining context
  * Remembering user data

---

### 4. Google Sheets (Product Database)

* Contains product data (computer devices)
* Used by the AI Agent as a data source:

  * Prices
  * Specifications
  * Availability

---

### 5. Gmail (Purchase Notification)

* Triggered only when:

  * The customer confirms a purchase
* Sends:

  * Customer name
  * Phone number
  * Requested product
* Delivered in a well-structured format

---

### 6. Telegram Response Node

* Sends the final response back to the customer via Telegram

---

## 🔄 Workflow Execution Flow

1. Customer sends a message via Telegram
2. Telegram Trigger receives the message
3. The message is passed to the AI Agent
4. The AI Agent:

   * Understands the request
   * Uses Google Sheets if needed
   * Generates a response
5. If the user wants to purchase:

   * The agent asks for name and phone number
   * Prepares an email
   * Sends it to the store owner
6. The final response is sent back to the user

---

## 🧠 AI Behavior Rules

* Responses rely only on data from Google Sheets
* Email is sent only when:

  * The user explicitly requests a purchase
* The agent must collect:

  * Customer name
  * Phone number
* Responses should be:

  * Clear
  * Professional
  * User-friendly

---

## 🛠️ Requirements

To run this project, you need:

* n8n instance (local or cloud)
* Telegram Bot Token
* Google Sheets API access
* Gmail OAuth credentials
* Google Gemini API key

---

## 🚀 Setup Instructions

1. Open n8n
2. Import `workflow.json`
3. Add credentials:

   * Telegram
   * Gmail
   * Google Sheets
   * Gemini
4. Connect your Google Sheet (product data)
5. Activate the workflow

---

## 📂 Project Structure

```
/project-root
│
├── workflow.json
├── README.md
└── /docs (optional)
```

---

## 🔒 Security Notes

* Do NOT upload credentials to GitHub
* Use environment variables or n8n credentials manager
* Always protect:

  * API keys
  * OAuth tokens

---

## 💡 Future Improvements

* Payment integration
* Admin dashboard for order management
* Multi-language support
* Advanced memory (long-term context)
* Product recommendation system

---

## 🎯 Use Cases

* Computer stores
* eCommerce automation
* Customer support bots
* Lead generation systems

---

## 👨‍💻 Author

Ahmed Magdy
AI Automation Engineer

---

## ⭐ Notes

This project is a strong practical example of:

* Building AI Agents
* Integrating multiple tools in n8n
* Creating a fully automated sales system without a traditional backend

---

🔥 Future ideas:

* Connect it to a frontend application
* Turn it into a SaaS product
