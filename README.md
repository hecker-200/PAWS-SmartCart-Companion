# 🛒 PAWS SmartCart Companion

Welcome to **SmartCart Companion**, an AI-driven shopping assistant built to enhance customer experience and optimize in-store shopping with intelligent suggestions. Designed for the **Walmart Sparkathon**, this app demonstrates seamless ML + Backend + Frontend integration.

---

## 📁 Project Structure

```

PAWS-SmartCart-Companion/
├── backend/
│   ├── app.js               # Express server
│   ├── routes/              # API routes
│   ├── controllers/         # Logic for ML API consumption
│   └── .env                 # Environment variables (ML\_API\_URL)
├── ml/
│   ├── app.py               # Flask ML API (Product Generator)
│   ├── utils.py             # CSV cleaner + tag generator
│   ├── cleaned\_products.json # Auto-generated product DB
│   └── products.csv         # Raw data source
├── frontend/
│   ├── smartcart-walmart-guide/ # React frontend (search + results UI)
│   └── ...
└── README.md

````

---

## 🚀 How It Works

1. **Frontend (React + Tailwind)**  
   User enters a query like:  
   > `"monthly groceries under 400 rupees"`  
   This is sent via POST to the backend `/api/cart/generate`.

2. **Backend (Node.js + Express)**  
   The backend reads `.env` → calls ML API (`http://localhost:5050/generate`) with query text.

3. **ML API (Flask)**  
   - Parses input
   - Matches occasion-based or tag-based product sets
   - Filters by budget
   - Sends back JSON list of products

4. **Frontend (again)**  
   - Displays results as beautiful cards  
   - Auto image suggestion & sorting

---

## 🧠 ML Layer (CSV → JSON → Smart Cart)

- Uses `products.csv` with 25,000+ items
- `utils.py` cleans & extracts tags from category, brand, description, etc.
- Generates `cleaned_products.json` on startup
- Smart matching with budget filtering + tag/occasion logic

---

## 🌐 APIs

### POST `/api/cart/generate`
```json
{
  "input": "puja items under 150 rupees"
}
````

**Response:**

```json
{
  "products": [
    { "name": "Agarbatti", "price": 10, "tags": ["puja", "festive", ...] },
    ...
  ]
}
```

---

## 🛠 Setup Instructions

### Backend (Node.js)

```bash
cd backend
npm install
node app.js
```

### ML Server (Python Flask)

```bash
cd ml
pip install -r requirements.txt
python app.py
```

### Frontend (React)

```bash
cd frontend/smartcart-walmart-guide
npm install
npm start
```

---

## 📸 Product Images

(Upcoming):
Integration with a free cloud API or dummy CDN for auto image fetching for Indian products like Kurkure, Maggi, etc.

---

## 🔒 Env Setup

Create a `.env` in `/backend`:

```
ML_API_URL=http://localhost:5050/generate
```

---

## ✨ Features

* 🔍 Occasion + Tag-based product generation
* 💰 Budget filtering
* 📦 Auto-generated product list from CSV
* 🎨 Clean & responsive frontend cards
* ⚙️ Easily scalable with any product data

---

## 💡 Sparkathon Theme

> *Using AI to enhance in-store experience, improve decision-making, and personalize retail journeys for Indian consumers.*

---

## 🧑‍💻 Made by

PAWS – with 💙 for innovation & sleepless debugging

---


