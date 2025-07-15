#  HovMan Chatbot

A simple intent-based chatbot built with PyTorch. This project uses a feedforward neural network for natural language understanding, trained on custom intents. It recognizes user input and provides context-aware responses in real time.

---

##  Features

* ✅ Neural network built using PyTorch
* ✅ Intent classification from JSON-based training data
* ✅ Bag-of-words NLP pipeline using NLTK
* ✅ Customizable intents and responses
* ✅ Confidence-based response filtering
* ✅ CLI interface for quick testing
* ✅ Trained model stored as `data.pth`

---

##  Model Architecture

```text
Input Layer → Hidden Layer (ReLU) → Hidden Layer (ReLU) → Output Layer
```

* **Input size**: number of vocabulary tokens
* **Hidden size**: configurable (default = 8)
* **Output size**: number of intent tags
* **Loss**: CrossEntropyLoss
* **Optimizer**: Adam

---

##  Project Structure

```
├── intents.json         # Intent patterns & responses
├── nltk_utils.py        # Tokenization, stemming, bag-of-words
├── model.py             # NeuralNet class definition
├── train.py             # Training script (generates data.pth)
├── chat.py              # CLI chatbot interface
├── data.pth             # Saved model state
└── README.md
```

---

##  Installation & Setup

1. **Clone the repository**

```bash
git clone git@github.com:manuelhorvey/contextual_chatbot.git
cd hovman-chatbot
```

2. **Install dependencies**

```bash
pip install torch numpy nltk
```

3. **Download NLTK tokenizer**

```python
import nltk
nltk.download('punkt')
```

4. **Train the model**

```bash
python train.py
```

5. **Start chatting**

```bash
python chat.py
```

---

##  Example Interaction

```
You: Hi
HovMan: Hi there, what can I do for you?

You: What do you sell?
HovMan: We sell coffee and tea

You: Do you take Paypal?
HovMan: We accept VISA, Mastercard and Paypal

You: Bye
HovMan: See you later, thanks for visiting
```

---

##  Customization

Want to add your own intents and responses?

* Edit `intents.json`:

```json
{
  "tag": "your_tag",
  "patterns": ["user input variations"],
  "responses": ["your bot response"]
}
```

* Retrain the model:

```bash
python train.py
```

---

##  Performance Notes

This chatbot is not trained on large datasets and does not use advanced language models (like GPT or BERT). It's lightweight, fast, and great for small-scale or demo applications. Perfect for learning the fundamentals of chatbot development.

---

##  License

MIT License. Free for personal and commercial use. Attribution appreciated.

---
