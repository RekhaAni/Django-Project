 # 🖼️ Graphical Password Authentication System for Information Security

## Project Overview

This project implements a **secure and innovative Graphical Password Authentication System** using the **Django** framework. It is designed to enhance **information security** by replacing or supplementing traditional text-based passwords with a sequence of user-defined interactions on a graphical interface. This system is a strong defense against common cyber threats.

The core principle involves a user selecting a series of **points (pass-points)**, regions, or images on a static background image during registration. At login, the user must replicate this **exact sequence and spatial configuration** to gain access.

---

## 🛡️ Security and Authentication Concepts

The Graphical Password System offers superior security compared to traditional text-based systems by specifically mitigating:

| Attack Type | Traditional Password Vulnerability | Graphical Password Mitigation |
| :--- | :--- | :--- |
| **Keylogging** | The password string is captured via keyboard strokes. | Input is a series of mouse/touch coordinates (X, Y) which are not captured by a keylogger, rendering the logged data useless for a login attempt. |
| **Shoulder Surfing** | The sequence of characters is easily observable. | The password relies on precise spatial memory and a sequence of clicks, which is difficult for an observer to replicate accurately without knowing the exact target coordinates. |
| **Dictionary/Brute-Force**| Attackers can use pre-computed password lists. | The password space is vast (a combination of sequence and coordinates), making it computationally infeasible to brute-force or use dictionary attacks. |

### Secure Storage

Unlike storing hashed text passwords, this system securely stores a **cryptographic hash** of the ordered sequence of interaction data (e.g., `(x1, y1, t1), (x2, y2, t2), ...`). This data is unique per user and cannot be reverse-engineered to determine the original points.

---

## ✨ Features

* **Graphical Registration:** A user-friendly interface allows users to define their password by clicking a sequence of points on a base image.
* **Precise Coordinate Capture:** Captures and records the exact (X, Y) coordinates of each click for high-fidelity authentication.
* **Sequence Validation:** Authentication requires matching not just the points, but the **order** in which they were clicked.
* **Standard Django Security:** Leverages Django's built-in security features for CSRF protection, secure session management, and user model integrity.
* **Modularity:** Designed as a reusable Django app that can be integrated into existing projects for enhanced authentication.

---

## 💻 Prerequisites

Ensure you have the following software installed on your system:

* **Python** (3.8 or higher)
* **pip** (Python package installer)

---

## ⚙️ Installation Guide

Follow these steps to set up and run the project locally.

### 1. Clone the Repository

```bash
git clone [https://github.com/yourusername/graphical-password-auth.git](https://github.com/yourusername/graphical-password-auth.git)
cd graphical-password-auth
````

### 2\. Create and Activate a Virtual Environment

It is highly recommended to use a virtual environment:

```bash
# Create the environment
python -m venv venv

# Activate on Linux/macOS
source venv/bin/activate

# Activate on Windows
.\venv\Scripts\activate
```

### 3\. Install Dependencies

Install all required Python packages (including Django, and potentially `Pillow` for image handling) from the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

### 4\. Database Setup

Apply the database migrations to set up the necessary tables (user model, graphical password storage model, etc.):

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5\. Create a Superuser (Optional)

Create an administrative user to access the Django Admin interface:

```bash
python manage.py createsuperuser
```

### 6\. Run the Server

Start the local development server:

```bash
python manage.py runserver
```

The application will now be running and accessible at `http://127.0.0.1:8000/`.

-----

## ▶️ Usage

### Registration Flow

1.  Navigate to the **Registration** page (`/register/`).
2.  Enter a username and email.
3.  You will be presented with a **base image**.
4.  Define your graphical password by clicking a **sequence of unique points** on the image (e.g., a minimum of 4 clicks).
5.  Click 'Confirm Password'. The system hashes and stores the sequence data.

### Login Flow

1.  Navigate to the **Login** page (`/login/`).
2.  Enter your username.
3.  You will be shown the same base image used during registration.
4.  Replicate the **exact sequence** of clicks/interactions in the correct order.
5.  Upon successful sequence replication, you will be logged into the system.

-----

## 🤝 Contributing

We welcome contributions to improve the security and features of this system.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/new-security-enhancement`)
3.  Commit your Changes (`git commit -m 'Implement stronger coordinate hashing'`)
4.  Push to the Branch (`git push origin feature/new-security-enhancement`)
5.  Open a Pull Request

-----

 
