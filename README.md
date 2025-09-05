# Resume Platform

A simple resume builder with secure authentication, version tracking, and PDF export.

## Features
- Secure signup/login (email + username + password)
- Resume builder: personal details, education, experience, skills
- Version tracking per resume with one-click PDF download
- Dashboard to manage and edit resumes
- Admin panel for managing data

## Tech Stack
- Backend: Django
- Database: MySQL (with SQLite fallback for quick start)
- Frontend: HTML, CSS (Bootstrap), JavaScript
- PDF: xhtml2pdf

## Setup

### 1) Clone and create virtual environment
```bash
git clone <your-repo-url>.git
cd Resume
python -m venv .venv
. .venv/Scripts/activate  # Windows PowerShell: .venv\Scripts\Activate.ps1
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Configure environment
Create a `.env` file in the `Resume/` directory (same level as `manage.py`) if using MySQL:
```env
DJANGO_SECRET_KEY=change-me
DJANGO_DEBUG=1
DJANGO_ALLOWED_HOSTS=*
DB_ENGINE=mysql
MYSQL_DATABASE=resume_db
MYSQL_USER=root
MYSQL_PASSWORD=your_password
MYSQL_HOST=127.0.0.1
MYSQL_PORT=3306
```
If you prefer quick start, omit `DB_ENGINE` or set it to `sqlite` to use a local SQLite database.

### 4) Initialize database
```bash
python manage.py makemigrations
python manage.py migrate
python manage.py createsuperuser  # optional
```

### 5) Run the server
```bash
python manage.py runserver
```
Open `http://127.0.0.1:8000/` in your browser.

## Usage
- Sign up or log in
- Create a resume, add education/experience/skills
- Save a version and download as PDF from the resume detail page

## Screenshots
Add screenshots to `screenshots/` and reference them here:
- Dashboard: `screenshots/dashboard.png`
- Resume editor: `screenshots/editor.png`
- PDF sample: `screenshots/pdf.png`

## Version Control
Use GitHub or GitLab. Example:
```bash
git init
git remote add origin https://github.com/yourname/resume-platform.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

## Notes
- To switch to MySQL, ensure `mysqlclient` is installed and set `.env` variables as shown.
- Static files are served via Django in development; collectstatic target is `staticfiles/`.
