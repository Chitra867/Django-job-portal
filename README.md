💼 Django Job Portal

A full-stack job portal built with Python and Django, designed to connect job seekers with employment opportunities through a streamlined recruitment platform.

The application provides job listings, application management, user authentication, profile management, and administrative tools.

✨ Features

👨‍💻 Job Seekers

Register and securely log in.

Browse available job opportunities.

View detailed job descriptions and requirements.

Apply for jobs and manage applications.

Create and update personal profiles.

Upload profile photos and supporting documents.

Track job application statuses.

🛠️ Administration

Manage job listings and applications.

Create, update, and delete job postings.

Manage registered users.

Review applications and update their statuses.

Manage contact messages and testimonials.

Access a dedicated administrative dashboard.

🌐 Additional Features

Responsive interface.

Role-based user access.

Contact form.

Testimonial submission and moderation.

Cloudinary integration for file uploads.

SQLite for local development and optional PostgreSQL support.

🧰 Technology Stack

Category

Technologies

Backend

Python 3.13, Django 6.0.1

Frontend

HTML5, CSS3, JavaScript, Django Templates

Database

SQLite, PostgreSQL

File Storage

Cloudinary

Static Files

WhiteNoise

Deployment

Gunicorn, Render-compatible configuration

Version Control

Git, GitHub

📂 Project Structure

Django-job-portal/
├── accounts/
├── jobs/
│   ├── migrations/
│   ├── static/
│   ├── templates/
│   ├── admin.py
│   ├── forms.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
├── myProject/
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
├── static/
├── .gitignore
├── manage.py
├── README.md
└── requirements.txt

🚀 Getting Started

Follow these steps to run the project locally.

1. Prerequisites

Make sure you have installed:

Python 3.13 or later within Django's supported Python versions

Git

A code editor such as Visual Studio Code

2. Clone the Repository

git clone https://github.com/Chitra867/Django-job-portal.git
cd Django-job-portal

3. Create a Virtual Environment

On Windows:

py -3.13 -m venv .venv

Activate the environment using PowerShell:

.\.venv\Scripts\Activate.ps1

Or using Git Bash:

source .venv/Scripts/activate

4. Install Dependencies

python -m pip install -r requirements.txt

5. Configure Environment Variables

Create a .env file in the project root, alongside manage.py.

DEBUG=True
SECRET_KEY=replace-with-your-own-random-secret-key

# Optional: PostgreSQL database
# DATABASE_URL=postgresql://USER:PASSWORD@HOST:5432/DATABASE

# Cloudinary configuration
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=

Generate a Django secret key locally:

python -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())"

Copy the generated value into your .env file.

Security: Never commit your .env file, API keys, database credentials, or other secrets to GitHub.

6. Set Up the Database

By default, the project uses SQLite when DATABASE_URL is not configured.

Run the database migrations:

python manage.py migrate

7. Create an Administrator Account

python manage.py createsuperuser

Follow the prompts to create your administrator credentials.

8. Start the Development Server

python manage.py runserver

Open your browser and visit:

Application: http://127.0.0.1:8000/

Django Admin: http://127.0.0.1:8000/admin/

⚙️ Production Deployment

Before deploying the application:

Set DEBUG=False and configure a secure SECRET_KEY.

Configure ALLOWED_HOSTS and CSRF_TRUSTED_ORIGINS.

Configure your production database and storage.

Use HTTPS and store credentials securely.

Run database migrations and collect static files.

Configure a production-compatible application server.

The project includes Gunicorn, WhiteNoise, and PostgreSQL-related dependencies. Production settings and deployment commands must be configured for the target hosting platform.

🔒 Security and Privacy

The repository excludes local environment files, virtual environments, SQLite databases, and uploaded media.

Never commit personal information, uploaded resumes, production database files, or credentials.

👨‍💻 Author

Chitra

GitHub: @Chitra867

Built with Python and Django.