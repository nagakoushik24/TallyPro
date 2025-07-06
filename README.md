# 💼 TallyPro – Scalable Enterprise Expense & Revenue Tracker

An end-to-end financial data engineering and reporting system inspired by Tally ERP, built using **Django**, **PostgreSQL**, and **Docker**, with features like PDF invoice generation, automated reporting, REST APIs, and scalable architecture.

---

## 🚀 Features

- 💳 Expense & Revenue tracking
- 🧾 Automated PDF Invoice generation (using ReportLab)
- 📧 Scheduled email reports (via Python `schedule` + `smtplib`)
- 📊 RESTful APIs using Django REST Framework
- 🗃️ PostgreSQL-backed persistence with Dockerized DB
- ⚙️ Fully containerized with Docker & `docker-compose`
- 🌐 Optional frontend via Angular or HTML templates

---

## 🧱 Tech Stack

- **Backend:** Django, DRF (Django REST Framework)
- **Database:** PostgreSQL
- **PDF Generator:** ReportLab
- **Automation:** schedule, smtplib
- **DevOps:** Docker, Docker Compose
- **Environment:** Conda-based development

---

## 📁 Project Structure

```

tallypro/
├── backend/
│ ├── requirements.txt
│ ├── manage.py
│ ├── tallycore/ # Django project
│ └── ledger/ # Django app for ledger entries
├── docker-compose.yml
├── Dockerfile
├── .env # Optional - environment variables
└── README.md

```

---

## ⚙️ Setup Instructions

### 🔧 1. Clone the Repo

```bash
git clone https://github.com/nagakoushik24/TallyPro.git
cd TallyPro
```

### 🐍 2. Create and Activate Conda Environment
```
conda create -n tallypro-env python=3.10
conda activate tallypro-env
```
### 📦 3. Install Dependencies
```
conda install -c conda-forge django djangorestframework psycopg2 reportlab schedule
pip install email-validator
```
### 🐳 4. Run with Docker Compose
```
docker-compose up --build
```
### ⚙️ 5. Apply Migrations
```
docker-compose exec web python manage.py migrate
```
### 👤 6. Create Superuser (Optional)
```
docker-compose exec web python manage.py createsuperuser
```

| Method | Endpoint       | Description             |
| ------ | -------------- | ----------------------- |
| GET    | `/api/ledger/` | List all ledger entries |
| POST   | `/api/ledger/` | Create new entry        |
| GET    | `/admin/`      | Admin dashboard         |


## 📤 Automation Scripts

- email_report.py → sends scheduled email invoices
- db_backup.sh → cron-scheduled backups of PostgreSQL DB
- generate_invoice.py → dynamic PDF invoices


