
# MedTrack – Medical Appointment Management System
## 📌 Overview

**MedTrack** is a cloud-based medical appointment management web application built using **Flask** and **AWS services**.

The system allows:

* Patients to book appointments
* Doctors to manage appointments
* Doctors to submit diagnoses
* Automated notifications using AWS SNS

The application uses **AWS DynamoDB** for database storage and integrates logging and health monitoring.

---

## 🚀 Features

### 👤 User Management

* User Registration (Doctor / Patient)
* Login & Logout system
* Session-based authentication
* Login count tracking

### 📅 Appointment Management

* Book appointments
* View appointments (Doctor & Patient)
* Search appointments by date

### 🩺 Diagnosis System

* Doctors submit diagnosis
* Appointment status updates automatically

### 🔔 Notifications

* AWS SNS sends notification when appointment is booked

### 📊 Monitoring

* Application logging
* Health check API endpoint

---
## 🏗️ Project Structure


```
Medtrack/
│
├── app.py
│
├── static/
│   └── css/
│       └── style.css
│
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   ├── doctor_dashboard.html
│   ├── patient_dashboard.html
│   ├── book_appointment.html
│   ├── view_appointment.html
│   ├── view_appointment_doctor.html
│   ├── view_appointment_patient.html
│   └── search_results.html
│
└── README.md
```

---

## ☁️ AWS Services Used

| Service        | Purpose                      |
| -------------- | ---------------------------- |
| DynamoDB       | Store users and appointments |
| SNS            | Appointment notifications    |
| IAM            | Secure AWS access            |
| EC2 (Optional) | Application hosting          |

---

## 🗄️ Database Design

### UsersTable

| Attribute   | Type                 |
| ----------- | -------------------- |
| email       | Primary Key (String) |
| name        | String               |
| password    | String               |
| role        | doctor/patient       |
| login_count | Number               |

---

### AppointmentsTable

| Attribute      | Type              |
| -------------- | ----------------- |
| appointment_id | Primary Key       |
| patient_email  | String            |
| doctor_email   | String            |
| date           | String            |
| time           | String            |
| status         | String            |
| diagnosis      | String (optional) |

---

## 🔧 Installation

### 1️⃣ Clone Repository

```bash
git clone https://github.com/your-username/medtrack.git
cd medtrack
```

### 2️⃣ Install Dependencies

```bash
pip install flask boto3
```

(Optional)

```bash
pip install -r requirements.txt
```

---

## ⚙️ AWS Configuration

Configure AWS credentials:

```bash
aws configure
```

Provide:

```
AWS Access Key ID
AWS Secret Access Key
Region: ap-south-1
```

---

## ▶️ Run Application

```bash
python app.py
```

Open browser:

```
http://localhost:5000
```

---

## 🌐 Application Routes

| Route                     | Description          |
| ------------------------- | -------------------- |
| /                         | Home page            |
| /register                 | Register user        |
| /login                    | Login                |
| /logout                   | Logout               |
| /doctor_dashboard         | Doctor dashboard     |
| /patient_dashboard        | Patient dashboard    |
| /book_appointment         | Book appointment     |
| /view_appointment_doctor  | Doctor appointments  |
| /view_appointment_patient | Patient appointments |
| /submit_diagnosis         | Submit diagnosis     |
| /search                   | Search by date       |
| /health                   | Health check         |

---

## 📝 Logging

Logs are saved in:

```
app.log
```

Example:

```
INFO - Appointment booked
```

---

## 🔒 Recommended Security Improvements

* Hash passwords using `bcrypt`
* Use environment variables for secrets
* Enable HTTPS
* Add role-based access validation
* Replace scan() with DynamoDB queries

---

## 🔮 Future Enhancements

* Appointment cancellation
* Email reminders
* Doctor availability calendar
* Admin dashboard
* REST API version
* Mobile app support

---

## 👨‍💻 Author

Peetla Sai Charan 
||📧 Email: peetlasaicharan@gmail.com
||📱 Phone: +91 8328229532

---

## 📄 License

Educational and open-source use free to use.
