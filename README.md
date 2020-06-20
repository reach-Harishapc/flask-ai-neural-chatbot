# 🧠 Flask AI Chatbot — Neural Network Powered Conversational Bot

An intelligent chatbot built with **Flask** and a custom **Keras deep learning model**. The bot uses a trained neural network with intent classification to understand user messages and generate contextual responses. Features NLP preprocessing with NLTK and a bag-of-words approach.

---

## ✨ Features

- **Deep Learning Model** — 3-layer Sequential neural network (128→64→softmax) trained on custom intents
- **Intent Classification** — Classifies user messages into 30+ intent categories with confidence scoring
- **NLP Pipeline** — Tokenization, lemmatization, and bag-of-words vectorization using NLTK
- **Personalized Responses** — Recognizes user names and personalizes replies
- **Custom Training** — Train the model on your own `intents.json` with the included training script
- **Web Interface** — Clean, interactive chat UI served via Flask

## 🛠️ Tech Stack

| Layer      | Technology                        |
|------------|-----------------------------------|
| Backend    | Python, Flask                     |
| ML Model   | Keras / TensorFlow (Sequential)   |
| NLP        | NLTK (WordNet Lemmatizer, Tokenizer) |
| Training   | SGD Optimizer, Categorical Crossentropy |
| Frontend   | HTML, CSS, JavaScript             |

## 📁 Project Structure

```
flask-ai-chatbot-2020/
├── app.py                  # Flask app with prediction & response logic
├── train.py                # Model training script (builds chatbot_model.h5)
├── intents.json            # Training data — 30+ intents with patterns & responses
├── chatbot_model.h5        # Pre-trained Keras model
├── words.pkl               # Serialized vocabulary
├── classes.pkl             # Serialized intent classes
├── static/
│   ├── css.css             # Chat widget styles
│   └── style.css           # Page styles
└── templates/
    └── index.html          # Chat interface
```

## 🚀 Getting Started

### Prerequisites

- Python 3.7+
- pip

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/flask-ai-chatbot-2020.git
cd flask-ai-chatbot-2020

# Install dependencies
pip install flask keras tensorflow nltk numpy

# Download NLTK data
python -c "import nltk; nltk.download('punkt'); nltk.download('wordnet'); nltk.download('omw-1.4')"
```

### Training the Model

```bash
python train.py
```

This will:
1. Parse `intents.json` and tokenize patterns
2. Build a bag-of-words representation
3. Train a 3-layer neural network for 200 epochs
4. Save the model to `chatbot_model.h5`

### Running the App

```bash
python app.py
```

The app will start at `http://127.0.0.1:5000/`

## 🧪 Model Architecture

```
Layer 1: Dense(128, activation='relu') + Dropout(0.5)
Layer 2: Dense(64, activation='relu')  + Dropout(0.5)
Layer 3: Dense(N, activation='softmax')  # N = number of intents
```

- **Optimizer:** SGD (lr=0.01, momentum=0.9, Nesterov)
- **Loss:** Categorical Crossentropy
- **Confidence Threshold:** 0.25

## 💬 Supported Intent Categories

Greetings, Goodbye, Thanks, Name Recognition, AI Knowledge, Robotics, Programming, Humor, Events, and 20+ more — all customizable via `intents.json`.

---

> **Note:** This project was built as a freelance project in 2020 demonstrating deep learning-based conversational AI with a custom-trained Keras model.
