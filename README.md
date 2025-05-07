# MOKSHA– AI-Powered Mental Health Chatbot

## Overview


MOKSHA is an intelligent, emotionally aware chatbot that provides empathetic conversational support to individuals experiencing stress, anxiety, or emotional distress. It combines state-of-the-art Natural Language Processing (NLP) models to simulate therapeutic dialogue while detecting potential crisis signals in real-time.

This project aims to demonstrate how artificial intelligence can be responsibly used to enhance mental health accessibility and early intervention.

## Features


✅ Emotion Classification: Detects the emotional tone of user input using a fine-tuned BERT-based emotion model.

✅ Dynamic UI Adaptation: Changes chat background color based on the user's emotional state (positive, negative, mixed).

✅ Crisis Detection: Flags high-risk inputs (e.g., suicidal ideation) using a binary classifier and suggests helpline resources.

✅ Empathetic Response Generation: Uses a fine-tuned Gemma 2B model to generate thoughtful, context-aware replies.

✅ Chat History Memory: Retains previous messages for coherent multi-turn conversations.

✅ Restartable Sessions: Users can reset the chat at any point with a goodbye message and new conversation window.

## Tech Stack


Python, Flask – Backend logic & API

HTML/CSS/JavaScript – Frontend interface

Hugging Face Transformers – Model loading & inference

Gemma 2B – Response generation

BERT (nateraw/emotion) – Emotion classification

BERT (binary classifier) – Suicide risk detection

Google Colab (training & evaluation)

## Architecture

<img width="430" alt="Screenshot 2025-05-07 at 7 28 23 PM" src="https://github.com/user-attachments/assets/fa63d0a2-afd1-4523-b89c-de0605db8fed" />

## Execution

> Configure Your Project Environment
> Before launching the application, ensure the following:  
> a. Insert Hugging Face Access Token  
> In the chatbot_frontend.py file, include your Hugging Face token where required to access public models.  
>> from huggingface_hub import login  
>> login(token="your_huggingface_token_here")  # Replace with your token  
> **Your token is available from: https://huggingface.co/settings/tokens**


> Set Correct Path to Templates Folder
> Ensure the Flask app knows where to find your HTML file. In the Flask app initialization:
> > app = Flask(__name__, template_folder='templates')  
> > Make sure the index.html file is placed inside the templates/ folder relative to your script.  


> If running locally
>> pip install flask torch transformers bert-score  
>> python chatbot_frontend.py  
>> Open in browser: http://127.0.0.1:5000  


>If running in colab, use this code to create proxy server for flask
>> #Sever Link for the website  
>> from google.colab.output import eval_js  
>> print(eval_js("google.colab.kernel.proxyPort(5000)"))  


## Testing ChatBot

1. Type a message in the chatbox and press Enter to send it.  
2. The chatbot will:  
>> Classify your emotion  
>> Change background color accordingly  
>> Detect any crisis statements  
>> Generate a supportive and context-aware response  

3. Type "exit" to end the chat and activate the restart button.  


## Final Notes

1. Ensure all models (crisis detector, emotion classifier, response generator) are either:  
>> Downloaded locally and referenced correctly, or  
>> Accessed via Hugging Face using your token  
2. For performance, use GPU environments when possible (e.g., Colab GPU or local CUDA setup)  


