# 🤖 AWS Project: AI-Powered Chatbot with Amazon Lex & Bedrock

**Building a Cloud-Native RAG Chatbot for Thevest Travel Agency**

This project demonstrates how I've built an AI-powered chatbot that can answer questions about *Thevest Travel Agency*—its offers, services, and more. By the end, you’ll have a functional, cloud-native chatbot driven by Retrieval-Augmented Generation (RAG) using AWS’s scalable ecosystem.

---

## 🌐 Why This Project?

Generative AI and chatbots are reshaping industries—tools like ChatGPT, Copilot, and Gemini demonstrate the potential. But did you know you can create your own AI-driven chatbot using AWS services?

Leveraging Amazon Lex for the conversational interface, Amazon Bedrock for generative AI, and S3 for document storage, this project shows how to build a chatbot powered by Retrieval-Augmented Generation (RAG), customized to your own business data.

---

## 🤔 What is RAG (Retrieval-Augmented Generation)?

RAG is a hybrid architecture that first **retrieves relevant information** from a knowledge base (like documents stored in S3), then uses a **large language model** (like Claude or GPT) to **generate a context-aware, human-like response**.

### ✅ Advantages of RAG:
- Contextual and up-to-date responses
- Reduces hallucinations by grounding answers in real data
- Customizable to specific business content
- Scalable and secure via AWS

---

## 🗺️ Architecture Diagram
*(Image to be added here)*

---

## 🧱 Key AWS Services Used

- **Amazon Lex**: For the chatbot voice/text interface
- **Amazon Bedrock**: To access foundation models like Claude, Titan, and others
- **Amazon S3**: Document storage for your custom data

---

## 🛠️ Deployment Steps

### 📂 Step 1 – Upload Documents to Amazon S3

Amazon S3 serves as the document store for RAG.

- Create a bucket named `my-travel-agency-data`
- Enable server-side encryption
- Upload custom documents about the agency (offers, services, etc.)
- *(Image showing uploaded files will be added)*

### 🧠 Step 2 – Request Access to Amazon Bedrock

Amazon Bedrock provides access to foundational models like Claude, Titan, Llama, DeepSeek, etc.

- Request access to the following models:
  - Titan Embeddings G1
  - Claude 2.1
- Wait for email confirmation or check the AWS Console
- *(Image to be added)*

### 📚 Step 3 – Configure Knowledge Base in Amazon Bedrock

- Create a Knowledge Base named `my-knowledge-base`
- Assign an appropriate IAM role
- Link it to the S3 bucket `my-travel-agency-data`
- Choose **Titan Embeddings G1 - Text v1.2** as the embedding model
- Sync your knowledge base to generate vector indexes
- *(Image to be added)*

### 💬 Step 4 – Create an Amazon Lex Bot

Amazon Lex enables conversational interfaces via voice or text.

- Create a bot and define intents:
  - `WelcomeIntent`: Greets the user and introduces the bot
  - `FallbackIntent`: Handles unrecognized input
  - `QnAIntent`: Uses Amazon QnAIntent connected to the Claude model and your knowledge base
- Link QnAIntent to the Bedrock knowledge base via its ID
- *(Image to be added)*

### 🧪 Step 5 – Build and Test

- Click **Build** and wait for Lex to compile the bot
- Test conversations using the chatbot interface
- *(Screenshots of successful interactions to be added)*

✅ The bot is now fully functional and can be integrated into web or mobile applications!

---

## 📌 Conclusion

In today’s competitive market, businesses must deliver fast and effective support. Generative AI makes that possible by enabling smarter and more context-aware interactions.

By integrating Amazon Lex and Bedrock, this project demonstrates how to create a dynamic, customized chatbot that not only answers user questions but also understands the specific needs of a business.

---

## ✍️ Author

**Made with 💻 by Nidhal Labri**  
🔗 [LinkedIn](https://www.linkedin.com/in/nidhal-labri/)

