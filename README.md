# Recruitment & Online Examination Portal

A web-based Recruitment and Online Examination Portal developed using **Django**.  
This project provides a complete solution for conducting online exams with timed submissions, evaluation, and result management.

---

## 🚀 Features

### 👨‍💼 Admin Module
- Secure admin login
- Create and manage exams
- Add MCQ and descriptive questions
- Evaluate student answers
- Publish and view results

### 🎓 Student Module
- Student registration and login
- Attend exams with countdown timer
- Auto-submit exam when time expires
- Question palette navigation
- View submitted answers and results

### ⏱️ Exam Management
- Timer-based online exams
- Auto submission on time out
- Answers stored in JSON format
- Manual and automatic evaluation

---

## 🛠️ Technologies Used

- **Backend:** Python, Django 5.x
- **Frontend:** HTML, CSS, JavaScript
- **Database:** SQLite
- **Authentication:** Django Authentication
- **Version Control:** Git & GitHub

---

⚙️ Installation & Setup
✅ Step 1: Clone the Repository
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

✅ Step 2: Create Virtual Environment
python -m venv env

✅ Step 3: Activate Virtual Environment
Windows
env\Scripts\activate
Linux / macOS
source env/bin/activate

✅ Step 4: Install Dependencies
pip install -r requirements.txt

▶️ How to Run the Server
✅ Step 5: Apply Migrations
python manage.py makemigrations
python manage.py migrate

✅ Step 6: Create Superuser (Admin)
python manage.py createsuperuser
Enter:
Username
Email
Password

✅ Step 7: Start the Development Server
python manage.py runserver


You will see:
Starting development server at http://127.0.0.1:8000/

✅ Step 8: Open in Browser

Application Home
http://127.0.0.1:8000/

Admin Panel
http://127.0.0.1:8000/admin/

🛑 Stop the Server

Press:
CTRL + C


