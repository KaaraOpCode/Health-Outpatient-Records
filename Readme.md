🏥 Digital Outpatient Visit Management System (DOVMS)

A secure, offline-capable digital outpatient card and visit management system designed to replace manual hospital cards while maintaining compatibility with legacy healthcare workflows.

This system digitizes patient outpatient records, visit logs, and audit trails, enabling healthcare facilities to improve efficiency, data integrity, and healthcare analytics.


---

📌 Problem Statement

Many healthcare facilities still rely on paper-based outpatient cards to record patient visits. These systems suffer from:

Lost or damaged patient cards

Illegible handwriting

Duplicate patient records

No analytics or reporting

Weak privacy and audit controls


This project provides a digital twin of the traditional outpatient card while enabling secure automation.


---

🎯 Project Objectives

Digitize outpatient visit records

Preserve legacy file numbers and workflows

Improve accountability and auditability

Enable analytics for healthcare planning

Support low-connectivity environments



---

🛠️ Technology Stack

Frontend

Flutter

Android-first (extensible to iOS/Web)

Offline-first architecture

QR-based patient lookup



Backend

Django

Django REST Framework (DRF)

JWT Authentication


Database

PostgreSQL

ACID-compliant

Secure relational storage



Optional Integrations

SMS / WhatsApp notifications

Biometric verification

Government health systems



---

🧩 System Architecture

[ Flutter Mobile App ]
        |
        | REST API (JSON)
        |
[ Django + DRF Backend ]
        |
[ PostgreSQL Database ]

Offline data sync ensures continuity in rural or low-connectivity clinics.


---

📂 Core Features

👤 Patient Management

Unique patient ID

Legacy file number support

Digital outpatient card (QR-based)

Secure patient profile


🗂️ Visit & Encounter Logging

Auto-timestamped visits

Department and doctor assignment

Structured clinical notes

Immutable visit history


👩‍⚕️ Healthcare Staff Management

Doctor and nurse profiles

Department mapping

Role-based permissions


🔐 Security & Audit

Role-Based Access Control (RBAC)

Encrypted data storage

Full audit logs

Immutable visit records


📊 Reporting & Analytics

Daily visit summaries

Department load statistics

Patient visit history

Public health trend insights



---

🧠 Data Model Overview

Patient

patient_id (UUID)

full_name

date_of_birth

gender

contact_details


Patient File

file_number

facility_id

status


Visit

visit_id

patient_id

department_id

doctor_id

visit_date

visit_time

notes


User (Staff)

role (admin / clerk / doctor / nurse)

facility_id



---

🔄 Workflow Comparison

Legacy Workflow

1. Patient carries paper card


2. Clerk manually writes visit


3. Doctor writes notes


4. No audit or analytics



Digital Workflow

1. Patient checks in via QR / ID


2. Visit auto-logged


3. Doctor records notes digitally


4. Secure storage & reporting




---

📱 Flutter App Features

Offline patient registration

QR code scanning

Fast patient search

Local encrypted storage

Sync on connectivity



---

⚙️ Backend Capabilities

RESTful APIs

JWT authentication

Role-based permissions

Audit logging middleware

Data validation & integrity



---

🔐 Security & Compliance

Encrypted credentials

Controlled access per role

Read/write restrictions

Full access logging


This design aligns with health data protection and audit requirements.


---

🌍 Localization & Accessibility

Multilingual support (English / Sesotho)

Low-bandwidth optimization

Print-friendly digital cards



---

🚀 Future Enhancements

Biometric patient verification

Smart queue management

Lab & pharmacy integration

National health ID linkage

AI-assisted diagnostics (future research)



---

🧪 Development Setup

Backend

pip install django djangorestframework psycopg2
python manage.py migrate
python manage.py runserver

Frontend

flutter pub get
flutter run


---

🤝 Stakeholders

Healthcare facilities

Ministry of Health

Public hospitals & clinics

Rural healthcare providers



---

📜 License

This project is intended for public service, research, and healthcare innovation.
Licensing to be defined based on deployment scope.


---

📣 Author

Tlokotsi Potloane
Healthcare Systems | Digital Transformation | Secure Systems Design
🇱🇸 Kingdom of Lesotho
