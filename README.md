# 🎓 Student Management System – Student Records Management Module

A full-stack web application designed to manage student records efficiently using **React**, **Django REST Framework**, and **MySQL**. The system provides complete **CRUD (Create, Read, Update, Delete)** functionality along with search, filtering, validation, and REST API integration.

---

## 📌 Project Overview

The **Student Records Management Module** is a web-based application that helps administrators manage student information digitally.

The application allows users to:

* Add new student records
* View all student records
* View individual student details
* Update existing student information
* Delete student records
* Search students
* Filter students by department and year
* Validate student information
* Communicate with the backend through REST APIs

---

## 🎯 Objectives

* To develop a simple and user-friendly student management system.
* To implement complete CRUD operations.
* To integrate a React frontend with a Django REST API.
* To store student information in a MySQL database.
* To implement client-side and server-side validation.
* To provide search and filtering functionality.
* To understand full-stack web application development.

---

## 🛠️ Technology Stack

| Technology            | Purpose                       |
| --------------------- | ----------------------------- |
| React.js              | Frontend development          |
| JavaScript            | Frontend logic                |
| HTML5                 | Page structure                |
| CSS3                  | Styling and responsive design |
| Django                | Backend framework             |
| Django REST Framework | REST API development          |
| MySQL                 | Database                      |
| Axios / Fetch         | API communication             |
| Postman               | API testing                   |
| Git                   | Version control               |
| GitHub                | Source code hosting           |

---

## 🏗️ System Architecture

```text
┌─────────────────────────┐
│      React Frontend     │
│       HTML / CSS / JS   │
└────────────┬────────────┘
             │
             │ REST API
             ▼
┌─────────────────────────┐
│   Django REST Framework │
│      Backend / API      │
└────────────┬────────────┘
             │
             │ Django ORM
             ▼
┌─────────────────────────┐
│        MySQL DB         │
│    Student Records      │
└─────────────────────────┘
```

---

## 📦 Module

### Student Records Management Module

The main module manages student information through CRUD operations.

### Features

#### ➕ Create Student

Allows the administrator to add a new student.

Student information includes:

* Register Number
* Student Name
* Email
* Phone Number
* Department
* Year
* Section
* Gender
* Date of Birth
* Address

#### 📖 Read Student

Displays all registered students in a table.

Users can also view individual student details.

#### ✏️ Update Student

Allows existing student information to be modified and saved.

#### 🗑️ Delete Student

Allows an administrator to remove a student record from the database.

#### 🔍 Search Student

Students can be searched using:

* Register Number
* Name
* Email

#### 🔽 Filter Students

Student records can be filtered using:

* Department
* Year
* Section

---

## 🔄 CRUD Operations

| Operation | HTTP Method | API Endpoint          |
| --------- | ----------- | --------------------- |
| Create    | POST        | `/api/students/`      |
| Read All  | GET         | `/api/students/`      |
| Read One  | GET         | `/api/students/{id}/` |
| Update    | PUT/PATCH   | `/api/students/{id}/` |
| Delete    | DELETE      | `/api/students/{id}/` |

---

## 🗄️ Database Structure

### Student Table

| Field         | Type    | Constraint  |
| ------------- | ------- | ----------- |
| id            | Integer | Primary Key |
| register_no   | VARCHAR | Unique      |
| name          | VARCHAR | Not Null    |
| email         | VARCHAR | Unique      |
| phone         | VARCHAR | Not Null    |
| department    | VARCHAR | Not Null    |
| year          | Integer | Not Null    |
| section       | VARCHAR | Not Null    |
| gender        | VARCHAR | Not Null    |
| date_of_birth | DATE    | Optional    |
| address       | TEXT    | Optional    |

---

## 📁 Project Structure

```text
student-management-system/
│
├── frontend/
│   ├── public/
│   └── src/
│       ├── components/
│       │   ├── StudentForm.jsx
│       │   ├── StudentList.jsx
│       │   └── StudentDetails.jsx
│       │
│       ├── pages/
│       │   ├── Dashboard.jsx
│       │   ├── AddStudent.jsx
│       │   └── EditStudent.jsx
│       │
│       ├── services/
│       │   └── studentApi.js
│       │
│       ├── App.jsx
│       └── main.jsx
│
├── backend/
│   ├── manage.py
│   ├── requirements.txt
│   │
│   ├── student_management/
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   │
│   └── students/
│       ├── models.py
│       ├── serializers.py
│       ├── views.py
│       ├── urls.py
│       └── admin.py
│
├── README.md
└── .gitignore
```

---

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone <your-github-repository-url>
```

```bash
cd student-management-system
```

---

### 2. Backend Setup

Navigate to the backend folder:

```bash
cd backend
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the virtual environment.

**Windows:**

```bash
venv\Scripts\activate
```

Install required packages:

```bash
pip install -r requirements.txt
```

---

### 3. Configure MySQL

Create a MySQL database:

```sql
CREATE DATABASE student_management;
```

Configure the database settings in Django:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'student_management',
        'USER': 'root',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

> Do not commit your actual database password to GitHub. Use environment variables for real projects.

---

### 4. Run Migrations

```bash
python manage.py makemigrations
```

```bash
python manage.py migrate
```

---

### 5. Start Django Server

```bash
python manage.py runserver
```

Backend will normally run at:

```text
http://127.0.0.1:8000/
```

---

### 6. Frontend Setup

Open another terminal and navigate to the frontend:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start React:

```bash
npm run dev
```

The frontend will normally run at:

```text
http://localhost:5173/
```

---

## 🧪 API Testing

The REST APIs can be tested using **Postman**.

### Create Student

```http
POST /api/students/
```

Example JSON:

```json
{
    "register_no": "24ECE001",
    "name": "Arun Kumar",
    "email": "arun@example.com",
    "phone": "9876543210",
    "department": "ECE",
    "year": 2,
    "section": "A",
    "gender": "Male",
    "date_of_birth": "2006-05-15",
    "address": "Coimbatore"
}
```

### Get Students

```http
GET /api/students/
```

### Get Individual Student

```http
GET /api/students/1/
```

### Update Student

```http
PUT /api/students/1/
```

### Delete Student

```http
DELETE /api/students/1/
```

---

## ✅ Validation

The application performs validation for:

* Empty required fields
* Duplicate register numbers
* Duplicate email addresses
* Invalid email formats
* Invalid phone numbers
* Invalid year values
* Invalid student IDs

Both **frontend and backend validation** should be implemented.

---

## 🧪 Testing

| Test Case                     | Expected Result              |
| ----------------------------- | ---------------------------- |
| Add valid student             | Student successfully created |
| Add student with empty fields | Validation error displayed   |
| Add duplicate register number | Duplicate error displayed    |
| View students                 | All records displayed        |
| Search student                | Matching records displayed   |
| Edit student                  | Updated data displayed       |
| Delete student                | Record removed               |
| Invalid student ID            | Appropriate error returned   |
| Backend unavailable           | Error message displayed      |

---

## 🔐 Security

* Database credentials should not be hard-coded.
* Use environment variables for sensitive information.
* Validate user input on both frontend and backend.
* Do not upload passwords or secret keys to GitHub.
* Use `.gitignore` for virtual environments and sensitive files.

---

## 🚀 Future Enhancements

The following features can be added in future versions:

* 🔐 User authentication and authorization
* 📊 Student dashboard and statistics
* 📅 Attendance management
* 📝 Marks and grade management
* 📄 Student report generation
* 📥 Export student data to Excel/PDF
* 🖼️ Student profile photo
* 🔔 Notifications
* 🌐 Deployment to a cloud platform

---

## 🎓 Learning Outcomes

Through this project, students can learn:

* Full-stack web development
* React component development
* Django REST API development
* MySQL database integration
* CRUD operations
* REST API concepts
* Frontend-backend integration
* Form validation
* API testing using Postman
* Git and GitHub
* Basic software project documentation

---

## 👨‍💻 Author

**LOGAVARDHAN**

Student Management System
Student Records Management Module

---

## 📄 License

This project is developed for **educational and academic purposes**.
