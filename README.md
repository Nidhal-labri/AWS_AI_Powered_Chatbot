# 🤖 AWS Project: AI-Powered Chatbot with Amazon Lex & Bedrock

**Building a Cloud-Native RAG Chatbot with Amazon Lex & Bedrock**

This project demonstrates how I’ve built an AI-powered chatbot that can answer questions about Thevest Travel Agency, such as its offers, services, and more. By the end, you’ll have a functional cloud-native chatbot driven by Retrieval-Augmented Generation (RAG) using AWS’s scalable ecosystem.

---

## 🌐 Why This Project?

Generative AI and chatbots are reshaping industries—tools like ChatGPT, Copilot, and Gemini demonstrate the potential. But did you know you can create your own AI-driven chatbot using AWS services?

Leveraging Amazon Lex for the conversational interface, Amazon Bedrock for generative AI, and S3 for document storage, you can build a Retrieval-Augmented Generation (RAG)-powered chatbot tailored to your own data.


---

## 🤔 What is RAG (Retrieval-Augmented Generation)?

RAG is a hybrid architecture that first retrieves relevant information from a knowledge base (like a database or S3 document store), then uses a language model (like Claude or Titan) to generate a response based on that information.

### ✅ Advantages of RAG:
- Provides factual, contextually accurate responses.
- Uses latest, custom, or private data not available in the base model.
- Reduces hallucination compared to pure generative models.
- Ensures data privacy by keeping knowledge sources under your control.

---

## 🗺️ Architecture Diagram
<img width="1920" height="1080" alt="3" src="https://github.com/user-attachments/assets/4e739a3d-c57d-41c0-8266-238c05223750" />

---

## 🧱 Key AWS Services Used

- **Amazon Lex**: For the chatbot voice/text interface
- **Amazon Bedrock**: To access foundation models like Claude, Titan, and others
- **Amazon S3**: Document storage for your custom data

---

## 🛠️ Deployment Steps

### 📂 Step 1 – Upload Documents to Amazon S3

S3 serves as the document store for RAG.
We create a bucket in S3 named `my-travel-agency-data` and enable encryption for security.
We upload the documents that contain information about our company (these documents were generated using ChatGPT). You can check them via [this link](https://github.com/Nidhal-labri/AWS_AI_Powered_Chatbot/tree/main/Used_Documents).

<img width="1919" height="875" alt="3" src="https://github.com/user-attachments/assets/bfaad63f-6425-45d9-ba5f-2c304d99a326" />

### 🧠 Step 2 – Request Access to Amazon Bedrock

Amazon Bedrock provides generative AI models like Claude, DeepSeek, LLaMA, Titan, and more to power RAG.

<img width="1918" height="811" alt="image_2025-07-29_15-23-00" src="https://github.com/user-attachments/assets/621832d4-02cb-4495-ab03-09e6179c610e" />

We request access to the desired models that we will use:
- Titan Embeddings G1
- Claude 2.1
We wait a few minutes, then receive emails confirming access has been granted—or we check access directly from the AWS console.

<img width="1919" height="836" alt="image_2025-07-29_15-23-22" src="https://github.com/user-attachments/assets/7ff14bf8-ce2d-42fb-977f-4126338779ec" />

### 📚 Step 3 – Configure Knowledge Base in Amazon Bedrock

I created a Knowledge Base in Amazon Bedrock and named it `my-knowledge-base`. I assigned the required service role to allow Bedrock to access the resources.

Open Amazon Bedrock and create a Knowledge Base.
Link the S3 bucket as the data source.
Sync the knowledge base to ensure the documents are indexed and searchable.

This knowledge base uses the previously created S3 bucket my-travel-agency-data as its data source.

For the embedding model, I chose **Titan Embeddings G1 - Text v1.2**, which outputs float vectors of 1536 dimensions. These embeddings are stored in Amazon S3 for later retrieval and comparison.

<img width="1284" height="1516" alt="Frame 1" src="https://github.com/user-attachments/assets/36048168-6b8c-4338-a0e2-069672f8b653" />

After the creation, we sync the data sources in the Amazon Bedrock knowledge base.

<img width="1919" height="882" alt="12" src="https://github.com/user-attachments/assets/ab450077-db62-462b-94ff-ee19c6b61f7e" />


### 💬 Step 4 – Create an Amazon Lex Bot

Amazon Lex is an AWS service that enables conversational AI with voice and text interfaces.
We create our bot and then configure the intents. An intent is a goal or purpose behind a user’s input—what the user wants to achieve by interacting with the chatbot.

We first create the following:

**WelcomeIntent**: Greets the user when the conversation starts and introduces the available services.
**FallbackIntent**: Triggered when the bot doesn’t understand the user's input. It politely asks the user to rephrase or try a different question.

Then we add Generative AI capability to the bot by creating an **AMAZON.QnAIntent** intent named QnAIntent that uses the Claude model by Anthropic. This intent is connected to the previously created Knowledge Base on Amazon Bedrock using its ID.
<img width="1074" height="365" alt="image" src="https://github.com/user-attachments/assets/dccb0b4d-5226-4684-813b-213ee0279d6f" />


### 🧪 Step 5 – Build and Test

We finally click on Build, wait a few seconds, and our bot will be ready for testing!
We test the draft version of the chatbot to confirm that it retrieves accurate and relevant information from our uploaded documents.
And here are some screenshots from the actual conversation with our chatbot!

<img width="3840" height="1283" alt="Bot" src="https://github.com/user-attachments/assets/ac6f0bb1-4157-4bc4-a29c-2f6e6af810c3" />

✅ Our bot is now fully functional, and ready to be UI-customized for integration into a website or mobile application!


---

## 📌 Conclusion

In today’s competitive market, businesses must deliver fast and effective support. Generative AI makes that possible by enabling smarter and more context-aware interactions.

By integrating Amazon Lex and Bedrock, this project demonstrates how to create a dynamic, customized chatbot that not only answers user questions but also understands the specific needs of a business.

---

## ✍️ Author

**Made with 💻 by Nidhal Labri**  
🔗 [LinkedIn](https://www.linkedin.com/in/nidhal-labri/)

