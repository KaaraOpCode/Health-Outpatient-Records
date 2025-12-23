📡 API Endpoint Documentation – Digital Outpatient Visit Management System (DOVMS)

Base URL:

https://api.dovms.example.com/

Authentication:

JWT Token required for all endpoints

Authorization: Bearer <access_token>



---

1. Authentication

1.1 Login

POST /api/auth/login/

Request Body

{
  "username": "doctor1",
  "password": "password123"
}

Response

{
  "access": "<jwt_access_token>",
  "refresh": "<jwt_refresh_token>"
}

Notes:

Use access token for subsequent API calls.

refresh token can be used to get new access token.



---

1.2 Refresh Token

POST /api/auth/refresh/

Request Body

{
  "refresh": "<jwt_refresh_token>"
}

Response

{
  "access": "<new_jwt_access_token>"
}


---

2. Patient Management

2.1 Get All Patients

GET /api/patients/

Response

[
  {
    "patient_id": "uuid-1234",
    "full_name": "Pohano Pohano",
    "date_of_birth": "2000-01-01",
    "gender": "M",
    "contact_details": "+26612345678",
    "file_number": "55983"
  }
]


---

2.2 Get Patient by ID

GET /api/patients/<patient_id>/

Response

{
  "patient_id": "uuid-1234",
  "full_name": "Pohano Pohano",
  "date_of_birth": "2000-01-01",
  "gender": "M",
  "contact_details": "+26612345678",
  "file_number": "55983"
}


---

2.3 Register New Patient

POST /api/patients/

Request Body

{
  "full_name": "Pohano Pohano",
  "date_of_birth": "2000-01-01",
  "gender": "M",
  "contact_details": "+26612345678",
  "file_number": "55984"
}

Response

{
  "patient_id": "uuid-5678",
  "message": "Patient successfully registered"
}


---

2.4 Update Patient

PUT /api/patients/<patient_id>/

Request Body

{
  "contact_details": "+26687654321"
}

Response

{
  "patient_id": "uuid-1234",
  "message": "Patient updated successfully"
}


---

3. Visits / Encounters

3.1 Log New Visit

POST /api/visits/

Request Body

{
  "patient_id": "uuid-1234",
  "department_id": "uuid-dept1",
  "doctor_id": "uuid-doc1",
  "visit_date": "2025-12-23",
  "visit_time": "09:30",
  "notes": "Routine check-up"
}

Response

{
  "visit_id": "uuid-visit1",
  "message": "Visit recorded successfully"
}


---

3.2 Get Visits for a Patient

GET /api/patients/<patient_id>/visits/

Response

[
  {
    "visit_id": "uuid-visit1",
    "department": "General Outpatient",
    "doctor": "Dr. Thabo",
    "visit_date": "2025-12-23",
    "visit_time": "09:30",
    "notes": "Routine check-up"
  }
]


---

3.3 Update Visit

PUT /api/visits/<visit_id>/

Request Body

{
  "notes": "Patient advised to take vitamins"
}

Response

{
  "visit_id": "uuid-visit1",
  "message": "Visit updated successfully"
}


---

4. Departments

4.1 Get All Departments

GET /api/departments/

Response

[
  {
    "department_id": "uuid-dept1",
    "name": "General Outpatient"
  },
  {
    "department_id": "uuid-dept2",
    "name": "Pediatrics"
  }
]


---

4.2 Add New Department

POST /api/departments/

Request Body

{
  "name": "Radiology"
}

Response

{
  "department_id": "uuid-dept3",
  "message": "Department added successfully"
}


---

5. Staff / Users

5.1 Get All Staff

GET /api/staff/

Response

[
  {
    "user_id": "uuid-doc1",
    "full_name": "Dr. Thabo",
    "role": "doctor",
    "department": "General Outpatient"
  }
]


---

5.2 Add New Staff

POST /api/staff/

Request Body

{
  "full_name": "Nurse Lebo",
  "username": "nurselebo",
  "password": "securepass",
  "role": "nurse",
  "department_id": "uuid-dept1"
}

Response

{
  "user_id": "uuid-nurse1",
  "message": "Staff added successfully"
}


---

6. Search & Filters

6.1 Search Patients

GET /api/patients/?search=<name_or_file_number>

6.2 Filter Visits by Date / Department

GET /api/visits/?start_date=2025-12-01&end_date=2025-12-23&department=uuid-dept1


---

🔒 Notes on Security & Best Practices

All endpoints require JWT token.

Sensitive patient data must be encrypted at rest.

Use HTTPS for all API calls.

Access to modify visits or patient records must be role-restricted.



---
