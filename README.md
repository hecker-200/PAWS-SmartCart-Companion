# 🛒 PAWS SmartCart Companion

**SmartCart Companion** is your AI-powered shopping assistant, crafted to simplify retail decisions using goal-based intent and budget prompts. Built with a modular Node + Flask + React stack, it integrates machine learning and a curated grocery dataset to deliver personalized cart suggestions.

---

## 🔧 Features

- 🧠 **Natural Language Cart Generation**  
  Input goals like _"Snacks under ₹100"_ or _"Puja items under ₹300"_ — get smart suggestions powered by an ML service.

- 💬 **Occasion-Based AI**  
  Understands intents like "college trip", "birthday", or "monthly groceries" using keyword classification.

- 🛍️ **Curated Product Database**  
  Built from a cleaned dataset of 25,000+ Indian grocery items.

- 🚀 **Seamless Frontend-Backend Integration**  
  React frontend talks to a Node backend, which in turn pings a Flask ML server.

- 🎯 **Budget-Aware Suggestions**  
  Always tries to fit products within your specified price range.

---

## 🗂️ Tech Stack

| Layer        | Tech                                                                 |
|--------------|----------------------------------------------------------------------|
| Frontend     | React + TailwindCSS + Vite                                           |
| Backend API  | Node.js + Express                                                    |
| ML Service   | Python + Flask                                                       |
| Data Source  | Cleaned CSV → JSON via custom parser                                 |

---

## 📊 Dataset Source

This project uses a cleaned version of the **BigBasket Product Dataset**:

🔗 [Indian Grocery Supermarket - BigBasket Dataset (Kaggle)](https://www.kaggle.com/code/ridamahmood005/indian-grocery-supermarket-big-basket-eda/input)

Credit to **Rida Mahmood** for curating this dataset.

---

## 🏁 How to Run Locally

### 1. Clone the Repo

```bash
git clone https://github.com/hecker-200/PAWS-SmartCart-Companion.git
cd PAWS-SmartCart-Companion
````

### 2. Install Frontend

```bash
cd frontend
npm install
npm run dev
```

### 3. Run Backend

```bash
cd ../backend
npm install
node app.js
```

### 4. Run ML API

```bash
cd ../ml
source venv/bin/activate  # or `venv\Scripts\activate` on Windows
python app.py
```

Make sure your `.env` file in `/backend` has the ML URL:

```
ML_API_URL=http://localhost:5050/generate
```

---

## 🚧 Roadmap

* 🔎 Improve NLP matching with transformer-based classification
* 📸 Add real product images using CDN/cloud sources
* 🧠 Expand ML to include item popularity, stock, and customer profiling
* 📱 PWA/mobile view with offline cart saving

---

## 🤝 Contributing

Wanna make SmartCart smarter? PRs are welcome!
Drop a star ⭐ if this saved you from shopping stress 😄

---

## 👨‍💻 Author

Made with ❤️ by PAWS

---
