# 🤖 n8n Telegram → LinkedIn Automation

This repository contains an **n8n workflow** that automates the process of posting **technology-related news articles** from a Telegram bot directly to LinkedIn.  
The workflow also updates the user on Telegram once the post is successfully published.

---

## 📌 Workflow Overview

The automation flow is as follows:

1. **Telegram Trigger Node**  
   - Listens for new messages/links from a Telegram bot.

2. **Code Node (Extract URL)**  
   - Cleans the message and extracts only the URL.

3. **HTTP Request Node (Fetch HTML)**  
   - Fetches the full HTML content of the news article.

4. **Code Node (Content Parser)**  
   - Parses the HTML and extracts:
     - **Title** 📰  
     - **Link** 🔗  
     - **Article Text** 📄  
     - **Image URL** 🖼️  

5. **Code Node (Prompt Formatting)**  
   - Prepares a structured prompt for the LLM to generate LinkedIn-ready content.

6. **HTTP Node (Groq LLM)**  
   - Calls the **Groq LLM API** to generate professional LinkedIn post content.

7. **HTTP Node (Image Conversion)**  
   - Converts the extracted image URL into a **data format** suitable for LinkedIn.

8. **LinkedIn Post Node**  
   - Publishes the generated post (with title, content, and image) to LinkedIn.

9. **Telegram Node (Confirmation Message)**  
   - Sends a success message back to the Telegram bot:  
     `"✅ Post successfully published on LinkedIn!"`

---

## 🚀 Features
- Automates content creation & posting to LinkedIn.  
- Uses **Groq LLM** for professional content generation.  
- Fully integrated with **Telegram → LinkedIn** workflow.  
- Sends confirmation updates to Telegram after posting.  

---

## 🛠️ Setup Instructions
1. Import `workflow.json` into your **n8n instance**.  
2. Configure the following credentials:
   - Telegram Bot API
   - Groq LLM API
   - LinkedIn API
3. Deploy the workflow (Render, Docker, or your own server).  

---

## 📂 Repository Structure
n8n-telegram-linkedin-automation/
├── workflow.json # Exported n8n workflow
└── README.md # Documentation


---

## 🙌 Credits
Created by **Sabarivenkatesh(https://github.com/Sabarivenkatesh3)**  
Powered by **n8n**, **Groq LLM**, and **LinkedIn API**.
