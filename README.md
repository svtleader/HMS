# Hospital Management System (HMS)

A web-based Hospital Management System built to digitalize and streamline the daily operations of a hospital or clinic — patient registration, doctor scheduling, and appointment booking — through a centralized platform.

> Course project for **CO2014 — Database Systems**, Faculty of Computer Science and Engineering, Ho Chi Minh City University of Technology (HCMUT).

## Overview

This system supports three core user roles — **Admin**, **Doctor**, and **Patient** — each with role-specific access and functionality:

- **Admin** — manages the system, approves doctors, and oversees overall data
- **Doctor** — views assigned patients, accesses patient records, and manages their specialization/availability
- **Patient** — books appointments, reports symptoms, and views their records

Appointments tie patients and doctors together with a date, time, and symptom description, and can be booked by either the admin or the patient.

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python (Django) |
| Database | MySQL |
| Frontend | HTML, CSS |

## Database

The conceptual model is built around the core entities **Patient**, **Doctor**, **Appointment**, **Administrator**, and **Users**, each mapped to a corresponding MySQL table (`HMS.PATIENT`, `HMS.DOCTOR`, `HMS.APPOINTMENT`, etc.) with appropriate primary/foreign key relationships — for example, an appointment references both a patient and a doctor.

Database access is handled directly through Django's raw SQL interface:

```python
from django.db import connection

with connection.cursor() as cursor:
    cursor.execute("SELECT * FROM HMS.DOCTOR;")
```

## Getting Started

### Prerequisites

- Python 3.x
- MySQL Server
- pip

### Installation

```bash
# Clone the repository
git clone https://github.com/svtleader/HMS.git
cd HMS/HospitalManagementSystem

# Install dependencies
pip install -r requirements.txt

# Apply database migrations
python manage.py migrate

# Run the development server
python manage.py runserver
```

Then open your browser to `http://127.0.0.1:8000/` to access the system.

## Team

Project by **Group 7 (CC01 - Team 7)**

| Name | Student ID |
|---|---|
| Nguyễn Phúc Nguyên (Leader) | 2352831 |
| Cao Lê Minh Khoa | 2352550 |
| Lê Dũng | 2252131 |
| Đinh Ngọc Việt | 2353317 |

**Instructor:** Đỗ Trường Thịnh

## License

This project was developed for academic purposes as part of the CO2014 Database Systems course.
