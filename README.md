# Virtual-Telecaller
---
## Overview

Virtual Telecaller is a web-based AI-powered voice assistant that handles real-time user interactions through a browser interface. It combines speech recognition for transcribing spoken queries, a fine-tuned Meta-LLaMA 3.2B-Instruct model for intelligent natural language responses, and text-to-speech (TTS) for delivering lifelike replies. Designed for customer support, lead generation, and appointment scheduling, it operates 24/7 as a scalable and cost-effective alternative to traditional telecalling systems.


## Live Demo
https://github.com/user-attachments/assets/300d5828-e7e5-4558-b779-fc7fd03737ea


## 🚀 Features

🎙️ **Live Voice Calling**  
Real-time voice communication enabled by **Zego Express SDK**

🗣️ **Speech-to-Text Transcription**  
Converts spoken input into text using accurate **speech recognition**

🧠 **AI-Powered Responses**  
Generates smart, context-aware replies with a fine-tuned **Llama-3.2B-Instruct** model trained on the *Bitext media LLM chatbot dataset*

🔊 **Text-to-Speech Output**  
Delivers natural, human-like responses using **TTS technology**

💬 **Interactive Chat Interface**  
Includes an alternative **chat-based interface** for text interaction

---

## 🧱 Architecture  
- **Frontend**: Built with React.js, featuring voice and chat interfaces  
- **Backend**: Flask API server handling communication and file operations  
- **Model Hosting**: Kaggle notebook running the fine-tuned Llama model  
- **Data Bridge**: Google Drive used as a bridge for file transfer due to limited compute resources  

---

## 🔄 Workflow  
1. User initiates a voice call through the frontend  
2. Speech is transcribed to text  
3. Transcribed text is sent to the Flask backend  
4. Backend uploads the transcribed text to Google Drive  
5. Kaggle notebook retrieves the input and processes it via LLM  
6. AI-generated response is saved back to Drive  
7. Backend fetches and forwards response to frontend  
8. Frontend displays and speaks the response via TTS  
9. Optionally, user can interact through a text-based chatbot interface  

---

## 🧠 Fine-Tuning Highlights  
The **Meta-Llama-3.2B-Instruct** model was fine-tuned using:

- 🧩 Transfer Learning with **LoRA** 
- ⚡ **Quantization** to reduce model size and enhance speed​ 
- 📋 **Instruction tuning** for improved responses
- 🔠 **tokenization** for effective text processing  
- 🚀 Training accelerated with **GPU/TPU** and **Flash Attention**  
- 📊 Performance tracked using **Weights & Biases** or **TensorBoard**  
- ⚙️ Optimized inference pipeline for near real-time response  

---

## 🛠️ Tech Stack  
- ⚛️ **React.js** (Frontend)  
- 📞 **Zego Express SDK** (Voice calling via WebRTC)  
- 🐍 **Flask** + **CORS** (Backend server)  
- ☁️ **Google Drive API** (Data bridge)  
- 🧠 **Meta-Llama-3.2B-Instruct** (Fine-tuned LLM)

---

## 📦 Prerequisites
- Node.js & npm
- Python 3.13.2
- Google Drive API credentials
- Zego API credentials

## ⚙️ Installation
```bash
# Clone repository
git clone [repository-url]
cd telecaller
```

# Frontend setup
```bash
cd frontend
npm install
```

# Backend setup
```bash
cd ../backend
pip install -r requirements.txt
```

### Configuration
1. Update Zego credentials in `ZegoCall.js`:
   ```bash
   const APP_ID = [your-app-id]
   const APP_SIGN = [your-app-sign]
   const TOKEN=[zego_call_token]
   ```

2. Configure Google Drive access in `final.py`:
   ```bash python
   SERVICE_ACCOUNT_FILE = 'path/to/credentials.json'
   YOUR_EMAIL = 'your-email@example.com'
   FOLDER_ID = 'your-drive-folder-id'
   ```

3. Set up model endpoints in `final.py`:
   ```bash python
   endpoint = "your-model-endpoint"
   token = "your-api-key"
   ```

### Running the Application
```bash
# Start backend
cd backend
python final.py
```

# Start frontend (in a new terminal)
```bash
cd frontend
npm run dev
npm start
```

---

## 💡Usage
1. Open the application in your browser
2. Click "Start Call" to begin a voice conversation
3. Speak naturally - your speech will be transcribed
4. The AI will process your query and respond both visually and audibly
5. Alternatively, use the chat interface by clicking "Open Chatbot"

---

## Future Improvements
- Direct API communication instead of Drive middleware with availabilty of more computational resources.
- Enhanced error handling and recovery
- User authentication and personalization
- Expanded training dataset for better responses

---
