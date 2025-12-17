# Student Crud X

A full-stack **Student Management System** that allows users to insert, update, view, and delete student records. Built with **React, Node.js, Express, and MySQL** to demonstrate CRUD operations, backend API integration, and a responsive user interface.

---

## Features
- Add new student records  
- Update existing student details  
- Delete student records  
- View all students in tabular format  
- Backend API integration  
- Form validations & error handling  
- Clean and responsive UI  

---

## Tech Stack
| Frontend | Backend | Database |
|----------|---------|----------|
| React.js | Node.js (Express) | MySQL |
| HTML / CSS | REST APIs | SQL |

---

## Installation

### Step 1: Clone the repo
```bash
git clone https://github.com/AnanyaGubba/Student-Crud-X.git
cd Student-Crud-X
```

### Step 2: Database Setup

1. **Create the database and table:**
   ```bash
   mysql -u root -p
   ```

2. **Database Setup**
   ```sql
   CREATE DATABASE student_crud_db;
   USE student_crud_db;
    
   CREATE TABLE students (
      id INT AUTO_INCREMENT PRIMARY KEY,
      name VARCHAR(255) NOT NULL,
      roll_no VARCHAR(50) NOT NULL UNIQUE,
      department VARCHAR(100) NOT NULL,
      year INT NOT NULL
   );
   ```

   Alternatively, use the provided SQL file:
   ```bash
    mysql -u root -p student_crud_db < student_crud.sql
   ```

### Step 3: Backend Setup

1. **Navigate to the project root**


2. **Install Application Dependencies
Install the Node.js packages required for the server and React frontend.**
   ```bash
   npm install
   ```

3. **Configure Database connection:**:
Open `server.js` and update mySQP credentials:
   ```javascript
   const db = mysql.createConnection({
    host: "localhost",
    user: "root",
    password: "YOUR_PASSWORD",
    database: "student_crud_db"
    });

   ```
4. **Start the backend server:**
   ```bash
   node server.js
   ```

   You should see:
   ```bash
   Server running on http://localhost:5000
   ```

5. **Frontend setup:**
   - Install frontend dependencies:
     ```bash
     npm install
     ```
   - Start the react application:
     ```bash
     npm start
     ```
   - Frontend will run at:
     ```bash
     http://localhost:3000
     ```

-----

##  Project Structure

```
Student-Crud-X/
├── public/             # Static assets
├── src/                # React frontend source code
│   ├── components/     # Reusable UI components
│   ├── App.js          # Main React component
│   ├── App.css         # Application styling
│   └── index.js        # React entry point
├── server.js           # Express backend server
├── package.json        # Dependencies and scripts
├── student_crud.sql    # Database schema
└── README.md           # This file

```

---


##  API Endpoints

The backend server provides the following REST API endpoints:

### Get All Students
- **Endpoint:** `GET /students`
- **Description:** Fetch all student records

### Add Student
- **Endpoint:** `POST /students`
- **Description:** Insert a new student
- **Request body:**
  ```json
  {
  "name": "John Doe",
  "roll_no": "CS101",
  "department": "CSE",
  "year": 2
  }
  ```

### Update Student
- **Endpoint:** `PUT /students/:id`
- **Description:** Update student details by ID

### Delete Student
- **Endpoint:** `DELETE /students/:id`
- **Description:** Delete student record by ID


-------


## Features In Detail
### Frontend Features
- React Hooks (`useState`, `useEffect`)
- Controlled forms with validation
- Dynamic table updates after CRUD actions
- Responsive layout for desktop and mobile
### Backend Features
- RESTful API architecture
- Express.js routing
- MySQL database integration
- Input validation and error handling
- SQL queries using parameterized statements
--------

## UI/UX Features
- Simple and clean layout
- Student records displayed in table format
- Clear Add / Update / Delete buttons
- User-friendly forms
- Instant UI updates after operations
-----------

## Validation Rules
- **Name:** Required
- **Roll Number:** Required & unique
- **Department:** Required
- **Year:** Required (numeric)

----------

## Future Enhancements
- Future Enhancements
- Search students by name or roll number
- Pagination for large datasets
- Authentication and role-based access
- Export student data to CSV
- Sorting and filtering options
