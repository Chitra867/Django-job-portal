Job Portal
A Django-based job portal connecting job seekers and employers. Browse openings, submit applications, manage job postings, and review applications through role-based workflows.
Features
- Job seekers: Register, sign in, manage a profile, browse job listings, view job details, apply for jobs, and track applications.
- Employers: Role-based accounts and job-posting workflows.
- Administration: Manage jobs, users, applications, contact messages, and testimonials through a dedicated dashboard and Django admin.
- Applications: Upload supporting files and track application statuses (applied, under review, shortlisted, rejected, or selected).
- Community: Contact form and moderated testimonials.
Tech stack
- Backend: Python 3.13, Django 6.0.1
- Database: SQLite for local development; optional PostgreSQL through DATABASE_URL
- Frontend: Django templates, HTML, CSS, and JavaScript
- Files: Cloudinary integration for profile photos and application attachments
- Static assets: WhiteNoise
Getting started (Windows / Git Bash)
Prerequisites
Install Python 3.13 and Git. If using Cloudinary-backed upload features, obtain your own Cloudinary credentials.
1. Clone and enter the repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
The repository root should contain manage.py and requirements.txt.
2. Create and activate a virtual environment
py -3.13 -m venv .venv
source .venv/Scripts/activate
python -m pip install -r requirements.txt
3. Set local environment variables
Create a .env file alongside manage.py and supply your own values as appropriate:
DEBUG=True
SECRET_KEY=replace-with-your-own-random-django-secret-key
# Optional: unset DATABASE_URL to use local SQLite.
# DATABASE_URL=postgresql://USER:PASSWORD@HOST:5432/DATABASE
# Required for Cloudinary-backed file uploads:
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
Generate a secret key locally using Django's get_random_secret_key(); never commit .env or real credentials. The project uses SQLite when DATABASE_URL is not set. Cloudinary-dependent file uploads require valid Cloudinary configuration.
4. Initialize the database and run the server
mkdir -p static
python manage.py check
python manage.py migrate
python manage.py runserver
Open http://127.0.0.1:8000/. For local administrator access, create an account with python manage.py createsuperuser and visit http://127.0.0.1:8000/admin/.
Keep your existing local db.sqlite3 when working with real or test data. Back it up before running migrations. A fresh clone starts with an empty database.

Project structure
.
├── jobs/                  # Models, views, routes, templates, migrations
├── myProject/             # Django settings and project URL configuration
├── manage.py              # Django management entry point
├── requirements.txt       # Python dependencies
└── static/                # Additional static assets (create if absent)
Configuration and deployment
Set DEBUG=False and use a strong, private SECRET_KEY in production. Configure hostnames, HTTPS, PostgreSQL (DATABASE_URL), and Cloudinary credentials for the deployment environment. Run database migrations and collect static assets as required by your host. The repository includes Gunicorn and WhiteNoise dependencies, but deployment must be configured separately for the target platform.
Do not commit .env, databases containing user data, uploaded resumes or photos, virtual environments, or generated static files. If secrets were previously committed, removing them from the latest commit is not sufficient: rotate the affected credentials and clean repository history before making it public.
Status
Local Django configuration has been checked successfully in a Windows Python 3.13 environment. End-to-end application and deploym