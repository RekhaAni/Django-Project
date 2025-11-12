# Django-Project
# 🖼️ Graphical Password Authentication System

## Project Overview

This project implements a **secure and innovative Graphical Password Authentication System** using the **Django** framework. It is designed to enhance information security by replacing or supplementing traditional text-based passwords with a sequence of user-defined interactions on a graphical interface, such as clicking specific points on an image or selecting a sequence of images.

The primary goal is to provide a more robust defense against common attacks like **keylogging**, **shoulder surfing**, and **dictionary attacks**.

---

## 🛡️ Security and Authentication Concepts

The system leverages the concept of **pass-images** or **pass-points** for user verification.

1.  **Increased Resistance to Keylogging:** Since the user's password input is a series of clicks/interactions rather than keystrokes, a keylogger will only record coordinate data or timestamps, which is far less useful than the actual password string.
2.  **Mitigation of Shoulder Surfing:** The sequence and spatial memory required make it more difficult for an observer to accurately replicate the full password without seeing the exact target coordinates.
3.  **Enhanced Usability and Memorability:** Graphical passwords often rely on human spatial and visual memory, making them easier to recall than complex alphanumeric strings.



---

## ✨ Features

* **Graphical Registration:** Users select a unique sequence of points, regions, or images to establish their graphical password.
* **Graphical Login:** Users authenticate by replicating the exact sequence and coordinates selected during registration.
* **Standard Django Integration:** Utilizes the robust security features and user management capabilities of the Django framework.
* **Secure Storage:** Password sequences are stored securely (e.g., using cryptographic hashing of the coordinate data or sequence identifiers) and never in plaintext.
* **Session Management:** Standard secure session and cookie handling provided by Django.

---

## 💻 Prerequisites

Before running this project, ensure you have the following installed:

* **Python** (3.8+)
* **pip** (Python package installer)

---

## ⚙️ Installation Guide

Follow these steps to get the project running on your local machine.

### 1. Clone the Repository

```bash
git clone [https://github.com/yourusername/graphical-password-auth.git](https://github.com/yourusername/graphical-password-auth.git)
cd graphical-password-auth

## Create a Virtual Environment (Recommended)
'''Bash

python -m venv venv
source venv/bin/activate  # On Linux/macOS
# .\venv\Scripts\activate # On Windows
3. Install Dependencies
Install the required Python packages (including Django):

'''Bash

pip install -r requirements.txt
(Note: Ensure requirements.txt includes Django and potentially Pillow for image handling.)

## Database Migrations
Apply the initial database migrations to set up the user and custom graphical password tables:

'''Bash

python manage.py makemigrations
python manage.py migrate

## Create a Superuser (Optional)
To access the Django Admin interface:

'''Bash

python manage.py createsuperuser

## Run the Server
Start the local development server:

'''Bash

python manage.py runserver
The application will now be accessible at http://127.0.0.1:8000/.

## ▶️ Usage
Registration
Navigate to the Registration page (/register/).

You will be prompted to select a base image.

Define your graphical password by clicking or interacting with the image in a specific sequence (e.g., 5 unique clicks).

Confirm the sequence. The system will securely store a hash of your sequence data.

Login
Navigate to the Login page (/login/).

You will be shown the same base image (or a randomized one, depending on the implementation).

Replicate the exact sequence of clicks/interactions you defined during registration.

If the replicated sequence matches the stored hash, you are successfully logged in.

## 🤝 Contributing
Contributions are what make the open-source community an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

Fork the Project

Create your Feature Branch (git checkout -b feature/AmazingFeature)

Commit your Changes (git commit -m 'Add some AmazingFeature')

Push to the Branch (git push origin feature/AmazingFeature)

Open a Pull Request
