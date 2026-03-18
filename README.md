# 🚀 Simple Flask Dockerized Web App

This is a simple web application built using **Python Flask** and containerized using **Docker**. The application provides basic API endpoints and demonstrates how to package and run an application inside a Docker container.

---

## 📌 Features

* Simple Flask web server
* Two API endpoints:

  * `/` → Welcome message
  * `/how_are_you` → Returns a response message
* Dockerized for easy deployment
* Lightweight and beginner-friendly project

---

## 🧱 Project Structure

```
simple-flask-app/
│── app.py
│── requirements.txt
│── Dockerfile
│── README.md
```

---

## 🐍 Application Code

### app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def home():
    return "Welcome Ben 🚀"

@app.route('/how_are_you')
def hello():
    return "I am good, how about you?"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

---

## 📦 Requirements

Create a `requirements.txt` file:

```
flask
```

---

## 🐳 Docker Setup

### Dockerfile

```dockerfile
FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY app.py .

CMD ["python", "app.py"]
```

---

## ⚙️ How to Run the Project

### 1️⃣ Build Docker Image

```bash
docker build -t simple-flask-app .
```

---

### 2️⃣ Run Docker Container

```bash
docker run -p 5000:5000 simple-flask-app
```

---

### 3️⃣ Access Application

Open your browser and go to:

* http://localhost:5000
* http://localhost:5000/how_are_you

---

## 🧠 Concepts Covered

* Docker Image creation
* Containerization
* Dependency management using `requirements.txt`
* Port mapping
* Basic Flask API development

---

## 🚀 Future Improvements

* Add database (MySQL / PostgreSQL)
* Deploy on AWS EC2
* Push image to Docker Hub
* Add CI/CD pipeline (GitHub Actions)
* Use Gunicorn for production

---

## 💼 Author

**Adinath Phad (Ben)**
Aspiring Cloud & DevOps Engineer 🚀

---

## ⭐ Note

This project is created for learning Docker and cloud deployment fundamentals.
