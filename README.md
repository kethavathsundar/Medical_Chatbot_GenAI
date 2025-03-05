# Medical Chatbot - AI-Powered Healthcare Assistant

## 📌 Overview
This project is a **Medical Chatbot** powered by **Cohere API** and **Pinecone Vector Database** for retrieval-augmented generation (RAG). It helps users with medical-related queries using **LLM-based responses** and relevant document retrieval.

## 🚀 Features
- **AI-Powered Responses**: Uses **Cohere LLM** to generate human-like answers.
- **Retrieval-Augmented Generation (RAG)**: Fetches relevant medical information using **Pinecone Vector Database**.
- **Fast and Scalable**: Runs efficiently using optimized **LangChain** components.
- **Web Interface**: Flask-based web application for easy interaction.

---
## 🛠️ Tech Stack
- **Python** (Backend Logic)
- **Flask** (Web Framework)
- **Cohere API** (LLM-based responses)
- **Pinecone** (Vector Database for retrieval)
- **LangChain** (Orchestrating AI & retrieval pipeline)
- **GitHub** (Version Control)

---
## ⚙️ Installation & Setup

### **Step 1: Clone the Repository**
```bash
git clone https://github.com/yourusername/medical-chatbot.git
cd medical-chatbot
```

### **Step 2: Set Up Virtual Environment**
```bash
python -m venv venv
source venv/bin/activate  # On macOS/Linux
venv\Scripts\activate  # On Windows
```

### **Step 3: Install Dependencies**
```bash
pip install -r requirements.txt
```

### **Step 4: Set Up Environment Variables**
Create a `.env` file in the root directory and add the following API keys:
```
COHERE_API_KEY=your_cohere_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_ENV=your_pinecone_environment
```

### **Step 5: Run the Application**
```bash
python app.py
```
The application will start at `http://127.0.0.1:5000`

---
## 📚 How It Works

1. **User asks a medical question** via the web interface.
2. **Pinecone retrieves** relevant medical documents.
3. **Cohere LLM processes** the question with retrieved documents.
4. **The chatbot generates** an accurate and concise medical response.
5. **The response is displayed** on the web UI.

---
## 🛠️ Development Workflow

### **Version Control with Git**
#### **Check Status of Files**
```bash
git status
```
#### **Add Updated & New Files**
```bash
git add .
```
#### **Commit Changes**
```bash
git commit -m "Updated chatbot logic and UI"
```
#### **Push to GitHub**
```bash
git push origin main
```

---
## 🏗️ Project Structure
```
medical-chatbot/
│── static/              # Static files (CSS, JS, images)
│── templates/           # HTML templates
│── src/
│   ├── helper.py        # Helper functions
│   ├── prompt.py        # AI prompt templates
│── app.py               # Main Flask application
│── store_index.py       # Indexing script for Pinecone
│── requirements.txt     # Required dependencies
│── README.md            # Documentation
```

---
## 🛠️ Troubleshooting

### **1. Pinecone Index Already Exists**
**Error:** `PineconeApiException: Resource already exists`
**Solution:** Modify `store_index.py` to delete the existing index before creating a new one:
```python
pc.delete_index(index_name)
pc.create_index(name=index_name, dimension=384, metric="cosine")
```

### **2. Cohere Model Not Supported**
**Error:** `BadRequestError: model 'command-r' is not supported`
**Solution:** Use a valid Cohere model like `command`, `command-light`, or `command-nightly`.

### **3. Missing API Key**
**Error:** `ValidationError: Did not find cohere_api_key`
**Solution:** Ensure `.env` file contains `COHERE_API_KEY` and that it's loaded properly.
```python
from dotenv import load_dotenv
load_dotenv()
```

---
## 📜 License
This project is licensed under the MIT License.

---
## 🙌 Contributors
- **Your Name** - [GitHub Profile](https://github.com/yourusername)

---
## 🎯 Future Improvements
- Add **authentication** for user queries.
- Enhance **UI/UX** with chatbot animations.
- Expand **medical knowledge base** with more sources.

🚀 **Happy Coding!**

