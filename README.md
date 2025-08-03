## 💪 OmnifyFit – Fitness Studio Booking API

**OmnifyFit** is a simple, powerful, and developer-friendly **REST API** built with **Flask** and **SQLite**, enabling users to browse, book, and manage fitness classes. Designed with clarity, performance, and timezone accuracy, it's the perfect micro-project for showcasing backend development skills.

---

## 🚀 Quick Setup

### 1️⃣ Clone the Repo
```bash
git clone https://github.com/LikithGS11/OmnifyFit.git
cd OmnifyFit
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Run the Application
```bash
python app.py
```

🌐 Server running at: [http://127.0.0.1:5000](http://127.0.0.1:5000)

---

## 🧰 Technologies Used

- 🐍 Python 3
- 🔥 Flask – lightweight backend framework
- 🗃️ SQLite – embedded relational database
- 🌍 ZoneInfo – timezone conversion (Python 3.9+)
- 🖼️ HTML/CSS – for optional demo interface

---

## 🗂️ Project Structure

```
OmnifyFit/
├── app.py             # Main Flask app
├── create_db.py       # Script to seed class data
├── templates/         # HTML templates for frontend
│   └── base.html
├── static/            # Optional CSS/JS
├── requirements.txt   # Python dependencies
└── README.md          # This file
```

---

## 🧪 API Endpoints

### 📅 1. Get All Classes  
**GET** `/classes`  
Returns all available classes.

**Sample Response**
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

### 📝 2. Book a Class  
**POST** `/book`  
Book a class by sending a JSON payload.

**Request Body**
```json
{
  "class_id": 1,
  "client_name": "Riya Sharma",
  "client_email": "riya@example.com"
}
```

**Success Response**
```json
{
  "message": "Booking successful for Yoga at 2025-06-09T18:00:00+05:30"
}
```

**Error Response**
```json
{
  "error": "No slots available for this class"
}
```

---

### 📧 3. Get Bookings by Email  
**GET** `/bookings?email=riya@example.com`  
Returns bookings linked to a client’s email.

**Sample Response**
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

## 🕒 Timezone Handling

- All class times are stored in **UTC** inside the database.
- API responses return time in **UTC**.
- On the frontend (HTML), JavaScript auto-converts the datetime to the **user’s local timezone** using `toLocaleString()`.

---

## 🧘‍♂️ Class Types Overview

| Class Name       | Description                                                |
|------------------|------------------------------------------------------------|
| 🧘 Yoga           | Improve flexibility and mindfulness                        |
| 💃 Zumba          | Dance-based cardio to boost energy                         |
| 🔥 HIIT           | High-Intensity training for quick results                  |
| 🏋️ Strength Train | Muscle-building resistance workouts                        |
| 🕺 Dance Cardio    | Fun cardio routines with choreography                      |

---

## 🎥 Live Demo Walkthrough

▶️ **Loom Video Walkthrough**:  
[https://www.loom.com/share/4c5755f139bb425fb6e81ab7a0169e86](https://www.loom.com/share/4c5755f139bb425fb6e81ab7a0169e86)

---

## 🙋‍♂️ Author

**Likith G S**  
Python Developer | AI/ML Enthusiast  
📧 likithgs11@gmail.com  
🔗 [GitHub Profile](https://github.com/LikithGS11)

---

## 📄 License

This project is open for educational and portfolio use.  
© 2025 OmnifyFit. All rights reserved.
