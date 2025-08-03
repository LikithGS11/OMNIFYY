# 💪 OmnifyFit – Fitness Studio Booking API

OmnifyFit is a lightweight, timezone-aware booking API built with **Flask** and **SQLite**, allowing users to view, book, and manage fitness classes seamlessly. It’s a fast and beginner-friendly backend project — ideal for learning or real-world use.

---

## 📦 Features

- ✅ Browse available fitness classes
- 🧘 Book sessions with email confirmation
- 📧 View bookings via client email
- 🌐 Timezone handling with Python’s `zoneinfo`
- 🔥 Clean API built on Flask
- 🗃️ SQLite – lightweight and easy to set up

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/LikithGS11/OmnifyFit.git
cd OmnifyFit
```

### 2. Setup Virtual Environment (Recommended)

```bash
# Create environment
python -m venv venv

# Activate environment
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the App

```bash
python app.py
```

Visit your app at: [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

## 🧭 API Endpoints

### ➤ `GET /classes` – List all fitness classes

```json
[
  {
    "id": 1,
    "name": "HIIT Workout",
    "datetime": "2025-08-05T07:00:00+05:30",
    "instructor": "Meera Verma",
    "available_slots": 8
  }
]
```

---

### ➤ `GET /book`

**Params (JSON body or query):**
```json
{
  "class_id": 1,
  "client_name": "Ayaan Khan",
  "client_email": "ayaan@example.com"
}
```

**Success Response:**
```json
{
  "message": "Booking successful for HIIT Workout at 2025-08-05T07:00:00+05:30"
}
```

**Error Response:**
```json
{
  "error": "No slots available for this class"
}
```

---

### ➤ `GET /bookings?email=ayaan@example.com` – View user bookings

```json
[
  {
    "class_name": "HIIT Workout",
    "datetime": "2025-08-05T07:00:00+05:30",
    "instructor": "Meera Verma"
  }
]
```

---

## 🕓 Timezone Awareness

- All datetime entries are stored in **UTC** internally.
- API responses provide **ISO 8601** strings with timezones.
- Client/UI can convert to local timezone using JavaScript (`Intl.DateTimeFormat`).

---

## 🗂️ Project Structure

```bash
OmnifyFit/
├── app.py             # Main application
├── create_db.py       # DB seeding script
├── requirements.txt   # Dependencies
├── templates/         # Optional UI (HTML)
│   └── base.html
├── static/            # CSS or JS files (if any)
└── README.md
```

---

## 📽️ Loom Demo

🎥 [Watch Demo Walkthrough](https://www.loom.com/share/4c5755f139bb425fb6e81ab7a0169e86)

---

## 👨‍💻 Author

**Likith G S**  
Feel free to fork, star ⭐, or suggest improvements!

---
```
