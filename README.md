# OmnifyFit – Command Your Fitness Arena

Welcome to **OmnifyFit**, where fitness meets precision control. Designed like a mission-ready control panel for fitness studios, this platform lets you launch, schedule, and manage high-impact workout sessions with zero friction.

Built using Flask and styled with Tailwind CSS, OmnifyFit gives you real-time class bookings, timezone-aware scheduling, and a fast, minimal UI — all wired into a clean REST API. Think of it as your tactical hub for running classes like a pro.

From yoga and strength circuits to high-intensity blitz modes — you schedule, they book, OmnifyFit handles the rest.

Gear up. Get in. Let’s book some classes.

---

## 📦 Features

- View available fitness classes
- Book classes via API
- Track user bookings by email
- Timezone-aware datetime management
- HTML interface for user interaction
- Lightweight and fast setup using SQLite

---

## ⚙️ Setup Instructions

### 🔁 Clone the Repo

```bash
git clone https://github.com/LikithGS11/OmnifyFit.git
cd OmnifyFit
```

### 🐍 Create & Activate a Virtual Environment

```bash
# Create environment
python -m venv venv

# Activate on Windows
venv\Scripts\activate

# Activate on macOS/Linux
source venv/bin/activate
```

### 📥 Install Dependencies

```bash
pip install -r requirements.txt
```

### ⚙️ Initialize the Database

```bash
python create_db.py
```

### ▶️ Run the App

```bash
python app.py
```

Visit: [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

## 📁 Project Structure

```
OmnifyFit/
├── app.log
├── app.py
├── create_db.py
├── fitness.db
├── package.json
├── package-lock.json
├── README.md
├── requirements.txt
├── tailwind.config.js
├── input.css
├── output.css
├── src/
├── static/
│   └── fitness.jpg
├── templates/
│   ├── base.html
│   ├── home.html
│   ├── classes.html
│   ├── book.html
│   └── bookings.html
```

---

## 📌 API Endpoints

### 📍 1. View All Classes

**GET** `/classes`

**Response:**
```json
[
  {
    "id": 1,
    "name": "Yoga",
    "datetime": "2025-06-09T18:00:00+05:30",
    "instructor": "Aditi Sharma",
    "available_slots": 10
  }
]
```

---

### 📍 2. Book a Class

**GET** `/book`

**Sample Payload:**
```json
{
  "class_id": 1,
  "client_name": "Riya Sharma",
  "client_email": "riya@example.com"
}
```

**Success Response:**
```json
{
  "message": "Booking successful for Yoga at 2025-06-09T18:00:00+05:30"
}
```

**Error Response:**
```json
{
  "error": "No slots available for this class"
}
```

---

### 📍 3. View Bookings by Email

**GET** `/bookings?email=riya@example.com`

**Response:**
```json
[
  {
    "class_name": "Yoga",
    "datetime": "2025-06-09T18:00:00+05:30",
    "instructor": "Aditi Sharma"
  }
]
```

---

## 🌐 Timezone Handling

- Datetimes stored in **UTC**
- API responses return UTC
- Frontend (JS) auto-converts to **user’s local timezone**

---

## 🧪 Frontend

A basic HTML-based frontend powered by **TailwindCSS** is included under the `/templates` and `/static` folders.

---
---

## Feedback & Support 🚀

If this project helped you level up:

⭐️ Give it a star on [GitHub](https://github.com/LikithGS11/OmnifyFit)  
🐛 Found a bug or want a new feature? Open an issue and let’s squash it  
🛠 Want to build on it? Fork the repo and mod away

Thanks for checking out **OmnifyFit** — your fitness command center.  
Ready to join the squad? Let’s build something awesome together.

---

![OmnifyFit Banner](https://cdn.pixabay.com/photo/2016/11/22/19/15/workout-1850925_1280.jpg)

> *“Code hard, train harder.”*
