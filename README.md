# 💪 OmnifyFit – Fitness Studio Booking API

**OmnifyFit** is a lightweight and intuitive REST API designed for managing fitness class bookings with ease. Built using **Flask**, it provides endpoints for viewing, booking, and tracking fitness classes in real-time. The app includes a minimal frontend built with HTML and TailwindCSS and handles timezone-aware scheduling using Python's `zoneinfo`.

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

## 🎥 Loom Video Demo

🔗 [https://www.loom.com/share/4c5755f139bb425fb6e81ab7a0169e86](https://www.loom.com/share/4c5755f139bb425fb6e81ab7a0169e86)

---
