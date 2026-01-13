PS E:\Recruitment> python -m venv env
PS E:\Recruitment> .\env\Scripts\activate

(env) PS E:\Recruitment> pip install -r requirements.txt
Installing collected packages: pytz, whitenoise, wcwidth, vine, tzdata, sqlparse, six, redis, python-dotenv, psycopg2-binary, Pillow, packaging, numpy, et-xmlfile, colorama, billiard, asgiref, python-dateutil, prompt-toolkit, openpyxl, gunicorn, Django, click, amqp, pandas, kombu, djangorestframework, django-filter, django-cors-headers, click-repl, click-plugins, click-didyoumean, celery
Successfully installed Django-5.0.2 Pillow-10.0.0 amqp-5.3.1 asgiref-3.11.0 billiard-4.2.4 celery-5.5.3 click-8.3.1 click-didyoumean-0.3.1 click-plugins-1.1.1.2 click-repl-0.3.0 colorama-0.4.6 django-cors-headers-4.3.1 django-filter-23.2 djangorestframework-3.14.0 et-xmlfile-2.0.0 gunicorn-21.2.0 kombu-5.5.4 numpy-1.26.4 openpyxl-3.1.2 packaging-25.0 pandas-2.2.1 prompt-toolkit-3.0.52 psycopg2-binary-2.9.9 python-dateutil-2.9.0.post0 python-dotenv-1.0.1 pytz-2025.2 redis-4.5.5 six-1.17.0 sqlparse-0.5.4 tzdata-2025.2 vine-5.1.0 wcwidth-0.2.14 whitenoise-6.6.0

[notice] A new release of pip is available: 24.0 -> 25.3
[notice] To update, run: python.exe -m pip install --upgrade pip

(env) PS E:\Recruitment> django-admin startproject recruitment
(env) PS E:\Recruitment> cd .\recruitment\

(env) PS E:\Recruitment\recruitment> python manage.py startapp users
(env) PS E:\Recruitment\recruitment> python manage.py startapp applications
(env) PS E:\Recruitment\recruitment> python manage.py startapp exam
(env) PS E:\Recruitment\recruitment> python manage.py startapp results
(env) PS E:\Recruitment\recruitment> python manage.py startapp notifications

upadate apps into settings

defining user models --> customuser, department
add customuser,department in user\admin.py
    admin.site.register(Department)
    admin.site.register(CustomUser)

''' equivalent to decorator
@admin.register(Result)
class ResultAdmin(admin.ModelAdmin):
    list_display = ('student', 'exam', 'score', 'submitted_at') --> columns shown in the admin site
    search_fields = ('student__name', 'exam__title')            --> add search box, searching can done only by student_name, exam_title 
    list_filter = ('exam', 'submitted_at')                      --> add filteration
'''

exam, results, notifications, applications
similar process --> models.py and admin.py

created basic views and urls
for users, exam, applications
update these urls in main root urls

just created base template for the app and blank templates

python manage.py makemigrations
System check identified some issues:

WARNINGS:
?: (urls.W005) URL namespace 'users' isn't unique. You may not be able to reverse all URLs in this namespace
Migrations for 'applications':
  applications\migrations\0001_initial.py
    - Create model Application
  applications\migrations\0002_initial.py
    - Add field exam to application
  applications\migrations\0003_initial.py
    - Add field result to application
  applications\migrations\0004_initial.py
    - Add field student to application
Migrations for 'exam':
  exam\migrations\0001_initial.py
    - Create model Exam
    - Create model Question
    - Create model StudentExam
  exam\migrations\0002_initial.py
    - Add field department to exam
    - Add field exam to question
    - Add field exam to studentexam
    - Add field student to studentexam
    - Alter unique_together for studentexam (1 constraint(s))
Migrations for 'notifications':
  notifications\migrations\0001_initial.py
    - Create model Notification
  notifications\migrations\0002_initial.py
    - Add field recipient to notification
Migrations for 'results':
    - Create model Result
  results\migrations\0002_initial.py
    - Add field student to result
Migrations for 'users':
  users\migrations\0001_initial.py
    - Create model CustomUser
(env) PS E:\Recruitment\recruitment> python manage.py makemigrations
System check identified some issues:

WARNINGS:
?: (urls.W005) URL namespace 'users' isn't unique. You may not be able to reverse all URLs in this namespace
No changes detected
(env) PS E:\Recruitment\recruitment> python manage.py migrate       
System check identified some issues:

WARNINGS:
?: (urls.W005) URL namespace 'users' isn't unique. You may not be able to reverse all URLs in this namespace
Operations to perform:
  Apply all migrations: admin, applications, auth, contenttypes, exam, notifications, results, sessions, users
Running migrations:
  Applying applications.0003_initial... OK
  Applying applications.0004_initial... OK
  Applying notifications.0002_initial... OK
  Applying results.0002_initial... OK
(env) PS E:\Recruitment\recruitment>

Localhost url
http://localhost:8000
