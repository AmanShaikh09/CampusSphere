# College Student Management and Examination Portal

A full-stack web application for managing college academics, students, faculty, examinations, marks, results, fees, notifications, and role-based dashboards.

## Overview

This project is built for a college environment with separate access for Admin, Exam Cell, Faculty, Students, and Accountant users. It supports institutional email login, protected role-based routes, student profile management, exam workflows, marks entry, result processing, hall tickets, fee records, notifications, and a student-only forgot-password flow using Gmail OTP.

## Tech Stack

### Frontend

- React
- Vite
- React Router
- Tailwind CSS
- Axios
- Lucide React icons
- Recharts
- jsPDF, html2canvas, html-to-image
- xlsx
- qrcode

### Backend

- Python
- Flask
- Flask-CORS
- Flask-JWT-Extended
- Flask-PyMongo / PyMongo
- Werkzeug password hashing
- python-dotenv
- Gmail SMTP for password reset OTP

### Database

- MongoDB 

## Main Features

- Role-based login for Admin, Exam Cell, Faculty, Student, and Accountant
- Protected dashboards and routes based on user role
- Institutional email validation using `@mgmcen.ac.in`
- Admin student management
- Staff account creation for Faculty, Exam Cell, and Accountant
- Department, subject, and academic setup
- Exam setup and form workflows
- Internal and external marks management
- Result processing and result publishing
- Hall ticket generation and student hall ticket view
- Student profile, subjects, exams, fees, and results pages
- Accountant fee collection and partial payment records
- Notifications and audit logs
- Student-only forgot password using Gmail OTP

## Project Structure

```text
Final1/
|-- .git/                         # Git repository metadata
|-- .venv/                        # Local Python virtual environment
|-- .vscode/
|   |-- settings.json
|   `-- tasks.json
|-- backend/
|   |-- app/
|   |   |-- assets/
|   |   |   `-- signatures/
|   |   |       `-- director_signature.png
|   |   |-- models/
|   |   |-- routes/
|   |   |   |-- academic.py
|   |   |   |-- accountant.py
|   |   |   |-- analytics.py
|   |   |   |-- audit.py
|   |   |   |-- auth.py
|   |   |   |-- backlog.py
|   |   |   |-- dashboard.py
|   |   |   |-- eligibility.py
|   |   |   |-- exam.py
|   |   |   |-- exam_forms.py
|   |   |   |-- exam_notify.py
|   |   |   |-- exam_settings.py
|   |   |   |-- exam_setup.py
|   |   |   |-- external_marks.py
|   |   |   |-- hall_ticket.py
|   |   |   |-- internal_marks.py
|   |   |   |-- marks.py
|   |   |   |-- marks_verify.py
|   |   |   |-- reports.py
|   |   |   |-- result_processing.py
|   |   |   |-- result_publish.py
|   |   |   |-- revaluation.py
|   |   |   |-- seating.py
|   |   |   |-- supplementary.py
|   |   |   `-- timetable.py
|   |   |-- services/
|   |   |-- utils/
|   |   |   |-- decorators.py
|   |   |   |-- excel_processor.py
|   |   |   |-- helpers.py
|   |   |   |-- logger.py
|   |   |   |-- marks_import_utils.py
|   |   |   `-- validators.py
|   |   `-- __init__.py
|   |-- mongodb_data/              # Local MongoDB data files
|   |-- scratch/
|   |   |-- bulk_forward_lab_marks.py
|   |   |-- bulk_update_lab_att.py
|   |   |-- clean_subjects.py
|   |   |-- debug_db.py
|   |   |-- final_bulk_save_lab_marks.py
|   |   |-- random_fill_external_lab_marks.py
|   |   |-- random_fill_lab_marks.py
|   |   |-- update_subjects_sem2.py
|   |   `-- update_subjects_sem2_categories.py
|   |-- venv/                      # Backend virtual environment
|   |-- __pycache__/               # Python cache files
|   |-- .env
|   |-- analyze_dept_mismatch.py
|   |-- check_and_create_student_users.py
|   |-- check_apps.py
|   |-- check_database_status.py
|   |-- check_db_grade.py
|   |-- check_lock.py
|   |-- check_pdf_apps.py
|   |-- check_profile_data.py
|   |-- check_rahul.py
|   |-- check_students.py
|   |-- check_users_collection.py
|   |-- complete_student_data.py
|   |-- config.py
|   |-- crash.log
|   |-- create_accountant_user.py
|   |-- create_mismatch_report.py
|   |-- create_system_users.py
|   |-- DASHBOARD_FIX_REPORT.md
|   |-- debug_dashboard.py
|   |-- debug_subjects.py
|   |-- diagnostic_test.py
|   |-- error.log
|   |-- fee_details.txt
|   |-- find_admin.py
|   |-- fix_and_regenerate.py
|   |-- full_profile.txt
|   |-- import_csv.py
|   |-- list_exams.py
|   |-- mismatch_results.txt
|   |-- mismatch_results_utf8.txt
|   |-- out.log
|   |-- output.txt
|   |-- profile_debug.json
|   |-- profile_output.txt
|   |-- quick_password_check.py
|   |-- recalculate_grades.py
|   |-- regenerate_tickets_with_sig.py
|   |-- requirements.txt
|   |-- requirements_utf8.txt
|   |-- reset_password.py
|   |-- restore_object_ids.py
|   |-- revert_status.py
|   |-- run.py
|   |-- seed_db.py
|   |-- seed_fy1_cse_a_fees.py
|   |-- seed_fy_students.py
|   |-- seed_subject_codes.py
|   |-- setup_test_admin.py
|   |-- set_all_student_passwords.py
|   |-- set_all_users_passwords.py
|   |-- sync_student_fields.py
|   |-- test_admin_student_creation.py
|   |-- test_api.py
|   |-- test_dashboard.py
|   |-- test_dashboard_api.py
|   |-- test_env.py
|   |-- test_env2.py
|   |-- test_faculty_dash.py
|   |-- test_login_creds.py
|   |-- test_profile_endpoint.py
|   |-- test_razorpay_flow.py
|   |-- test_student_results.py
|   |-- tmp_check_db.py
|   |-- unlock_all.py
|   |-- update_all_hall_tickets.py
|   |-- update_fy_ids.py
|   |-- update_student_password.py
|   |-- verify_all_logins.py
|   |-- verify_all_passwords.py
|   |-- verify_api_endpoints.py
|   |-- verify_dashboard_fix.py
|   |-- verify_department_ops.py
|   |-- verify_exam_cell_endpoints.py
|   |-- verify_ids.py
|   |-- verify_new_aliases.py
|   |-- verify_output.txt
|   |-- verify_profile.py
|   |-- verify_real_students.py
|   `-- verify_repair.py
|-- frontend/
|   |-- dist/                      # Production build output
|   |-- node_modules/              # Frontend dependencies
|   |-- public/
|   |   |-- favicon.svg
|   |   |-- icons.svg
|   |   `-- qr-code.png
|   |-- src/
|   |   |-- assets/
|   |   |   |-- hero.png
|   |   |   |-- logo.png
|   |   |   |-- react.svg
|   |   |   |-- signature.png
|   |   |   `-- vite.svg
|   |   |-- components/
|   |   |   |-- common/
|   |   |   |   |-- Modal.jsx
|   |   |   |   |-- ProtectedRoute.jsx
|   |   |   |   |-- Table.jsx
|   |   |   |   `-- UI.jsx
|   |   |   `-- layout/
|   |   |       |-- DashboardLayout.jsx
|   |   |       |-- Header.jsx
|   |   |       `-- Sidebar.jsx
|   |   |-- context/
|   |   |   `-- AuthContext.jsx
|   |   |-- pages/
|   |   |   |-- accountant/
|   |   |   |   |-- AccountantDashboard.jsx
|   |   |   |   |-- AccountantFeeCollection.jsx
|   |   |   |   |-- AccountantPartialRecords.jsx
|   |   |   |   `-- AccountantStudents.jsx
|   |   |   |-- admin/
|   |   |   |   |-- AdminDashboard.jsx
|   |   |   |   |-- Allocation.jsx
|   |   |   |   |-- CreateAccount.jsx
|   |   |   |   |-- Departments.jsx
|   |   |   |   |-- Exams.jsx
|   |   |   |   |-- Faculty.jsx
|   |   |   |   |-- Inbox.jsx
|   |   |   |   |-- Notifications.jsx
|   |   |   |   |-- Reports.jsx
|   |   |   |   |-- Students.jsx
|   |   |   |   `-- Subjects.jsx
|   |   |   |-- auth/
|   |   |   |   |-- ForgotPassword.jsx
|   |   |   |   |-- Login.jsx
|   |   |   |   `-- ResetPassword.jsx
|   |   |   |-- common/
|   |   |   |   `-- UserNotifications.jsx
|   |   |   |-- examcell/
|   |   |   |   |-- Analytics.jsx
|   |   |   |   |-- AuditLogs.jsx
|   |   |   |   |-- Backlog.jsx
|   |   |   |   |-- Eligibility.jsx
|   |   |   |   |-- ExamCellDashboard.jsx
|   |   |   |   |-- ExamForms.jsx
|   |   |   |   |-- ExamNotifications.jsx
|   |   |   |   |-- ExamSettings.jsx
|   |   |   |   |-- ExamSetup.jsx
|   |   |   |   |-- ExternalMarks.jsx
|   |   |   |   |-- GradeSchema.jsx
|   |   |   |   |-- HallTicket.jsx
|   |   |   |   |-- InternalMarks.jsx
|   |   |   |   |-- MarksVerification.jsx
|   |   |   |   |-- ResultProcessing.jsx
|   |   |   |   |-- ResultPublish.jsx
|   |   |   |   |-- Revaluation.jsx
|   |   |   |   |-- Seating.jsx
|   |   |   |   |-- Supplementary.jsx
|   |   |   |   `-- Timetable.jsx
|   |   |   |-- faculty/
|   |   |   |   |-- FacultyDashboard.jsx
|   |   |   |   |-- FacultySubjects.jsx
|   |   |   |   |-- MarksEntry.jsx
|   |   |   |   `-- MarksOverview.jsx
|   |   |   |-- home/
|   |   |   |   |-- Home.css
|   |   |   |   `-- Home.jsx
|   |   |   `-- student/
|   |   |       |-- HallTicketPage.jsx
|   |   |       |-- StudentDashboard.jsx
|   |   |       |-- StudentExams.jsx
|   |   |       |-- StudentFees.jsx
|   |   |       |-- StudentProfile.jsx
|   |   |       |-- StudentResults.jsx
|   |   |       `-- StudentSubjects.jsx
|   |   |-- services/
|   |   |   `-- api.js
|   |   |-- utils/
|   |   |   `-- dateUtils.js
|   |   |-- App.css
|   |   |-- App.jsx
|   |   |-- index.css
|   |   `-- main.jsx
|   |-- .gitignore
|   |-- eslint.config.js
|   |-- index.html
|   |-- package-lock.json
|   |-- package.json
|   |-- postcss.config.js
|   |-- README.md
|   |-- tailwind.config.js
|   `-- vite.config.js
|-- generated/
|   `-- hall_tickets/
|       |-- HT-6B9A5C-2502127111246103.pdf
|       |-- HT-6B9A5C-2502127111246103_qr.png
|       |-- HT-6F7606-2502127111246101.pdf
|       |-- HT-6F7606-2502127111246101_qr.png
|       |-- HT-E1CF50-2502127111242061_qr.png
|       `-- HT-E1CF64-2502127111242076_qr.png
|-- Profile Images/
|-- venv/                          # Local Python virtual environment
|-- departments_export.csv
|-- dns_result.txt
|-- faculty_dataset.csv
|-- New FY-PRN List 25-26.xlsx
|-- pyrightconfig.json
|-- README.md
|-- real_data.json
|-- students_collection_export.csv
|-- students_export.csv
|-- students_export.csv.bak
|-- subjects_export.csv
`-- subject_export2.csv
```

## Prerequisites

- Node.js and npm
- Python 3.10 or later
- MongoDB connection string
- Gmail account with an App Password for OTP email sending

## Backend Setup

Go to the backend folder:

```bash
cd backend
```

Create and activate a virtual environment:

```bash
python -m venv venv
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Create or update `backend/.env`:

```env
SECRET_KEY=change-this-secret
JWT_SECRET_KEY=change-this-jwt-secret
MONGO_URI=your_mongodb_connection_string

FRONTEND_URL=http://localhost:5173
MAIL_USERNAME=yourgmail@gmail.com
MAIL_PASSWORD=your_gmail_app_password
MAIL_SENDER=yourgmail@gmail.com
```

Run the backend:

```bash
python run.py
```

The backend runs on:

```text
http://localhost:5000
```

## Frontend Setup

Go to the frontend folder:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Run the frontend:

```bash
npm run dev
```

The frontend runs on:

```text
http://localhost:5173
```



## Authentication

All login emails must end with:

```text
@mgmcen.ac.in  you may change according to Your Org.
```

Supported roles:

- Admin
- Exam Cell
- Faculty
- Student
- Accountant

JWT tokens are stored in browser local storage and used for authenticated API requests.

## Student Forgot Password Flow

The forgot-password feature is available only for students.

Flow:

1. Student clicks **Forgot password?** on the Student login page.
2. Student enters their institutional email.
3. Backend checks that the email belongs to a Student user and exists in the students collection.
4. A 6-digit OTP is sent through Gmail SMTP.
5. Student verifies OTP.
6. New password and confirm password fields appear.
7. Student changes password and returns to login.

OTP details:

- OTP expires in 10 minutes.
- OTP is single-use.
- OTP is stored hashed in MongoDB.
- Passwords are stored using Werkzeug password hashing.

## Useful Commands

Frontend build:

```bash
cd frontend
npm run build
```

Frontend lint:

```bash
cd frontend
npm run lint
```

Backend compile check:

```bash
python -m py_compile backend\app\routes\auth.py backend\config.py
```
#contact us if any query
1)Shaikh Aman Isakh -ashaikh49096@gmail.com
2)Choudante Apurwa -apurwachoudante05@gmail.com
3)Shivani Bande -shivanibande10@gmail.com
4)Akanksha Borgaonkar -akankshapsb07@gmail.com

## Important Notes

- Do not commit real `.env` secrets to version control.
- Gmail requires an App Password, not the normal Gmail account password.
- The frontend URL in `.env` should match the frontend address used by students.
- For local mobile testing, OTP is preferred over reset links because localhost links do not open correctly on other devices.
