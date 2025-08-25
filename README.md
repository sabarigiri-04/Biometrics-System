Biometric Attendance System
 Project Overview

This project is a biometric-based attendance system that uses face recognition for secure and automated entry/exit management.

Instead of traditional ID cards or manual sign-ins, staff can simply show their face to the webcam, and the system will:

Identify the person

Record entry and exit time

Store details securely in a MySQL database (XAMPP)

The system improves accuracy, prevents proxy attendance, and ensures reliable tracking of individuals.

⚙️ Features

👨‍💻 Staff registration with Name, ID, and captured face image

📷 Real-time face recognition using webcam

🗂️ Attendance logs stored in MySQL database

🕒 Automatic entry and exit detection

📊 Dashboard to view attendance records (Django frontend)

🔒 Secure login system for admin panel

🏗️ Tech Stack

Programming Language: Python 3.x

Framework: Django (for web interface)

Libraries & Tools:

OpenCV (face detection & image capture)

DeepFace / Face Recognition (model training & recognition)

NumPy, Pandas (data handling)

MySQL + XAMPP (database)

Frontend: HTML, CSS, Bootstrap

📂 Project Structure
Biometric-System/
│── biometric_app/        # Django app for attendance
│   ├── templates/        # HTML files
│   ├── static/           # CSS, JS, images
│   ├── views.py          # Main logic
│   ├── models.py         # Database models
│   ├── urls.py           # Routing
│── face_recognition/     # Face registration & recognition scripts
│   ├── register.py       # Register staff with captured face
│   ├── recognize.py      # Recognize faces via webcam
│── database/             # SQL scripts (attendance table)
│── manage.py             # Django entry point
│── requirements.txt      # Dependencies
│── README.md             # Documentation

 Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/your-username/biometric-system.git
cd biometric-system

2️⃣ Setup Virtual Environment & Install Dependencies
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
pip install -r requirements.txt

3️⃣ Configure MySQL Database

Start XAMPP (MySQL + Apache).

Create a database (e.g., biometric_db).

Import the provided attendance.sql file.

Update settings.py in Django with database credentials:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'biometric_db',
        'USER': 'root',
        'PASSWORD': '',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}

4️⃣ Run Migrations
python manage.py makemigrations
python manage.py migrate

5️⃣ Run the Web App
python manage.py runserver


Now open http://127.0.0.1:8000/

📷 Usage
📝 Staff Registration
python face_recognition/register.py


Enter staff details (Name, ID).

Capture face image via webcam.

🚪 Entry/Exit Recognition
python face_recognition/recognize.py


Webcam activates.

When a staff face is detected, system logs entry or exit time in database.

📊 Attendance Dashboard

Access via Django web interface.

Admin can filter attendance by date, staff, or department.

📈 Results & Benefits

✅ Eliminates manual/proxy attendance
✅ Faster entry/exit logging
✅ Secure storage in database
✅ Easy integration with HR systems

 Future Enhancements

Fingerprint + Face multi-modal biometric system

SMS/Email notifications for entry/exit

AI-based liveness detection (to avoid photo spoofing)

Cloud deployment (AWS/Azure)
