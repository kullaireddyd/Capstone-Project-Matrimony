
# Job Portal

## 📘 Job Portal Frontend (Angular 16 + Angular Material)

### 📁 Project Structure

```bash
job-portal/
├── frontend/        # Angular application
│   ├── src/
│   │   ├── app/
│   │   │   ├── components/
│   │   │   │   ├── job-list/
│   │   │   │   ├── job-details/
│   │   │   │   ├── job-form/
│   │   │   │   ├── job-application-form/
│   │   │   │   └── job-applications-list/
```

### 🚀 How to Run Frontend

```bash
cd frontend
npm install
ng add @angular/material
ng serve
```

✅ Runs at: `http://localhost:4200`

### 🧩 Components Overview

| Component Name               | Purpose                                       |
|-----------------------------|-----------------------------------------------|
| `JobListComponent`          | Displays all job listings                     |
| `JobDetailsComponent`       | Shows detailed view of a selected job         |
| `JobFormComponent`          | Form for creating/editing job listings        |
| `JobApplicationFormComponent` | Form for applicants to apply for a job    |
| `JobApplicationsListComponent` | Lists submitted job applications         |

### 🌐 Routes Overview

| Path                  | Component                     | Description                     |
|-----------------------|-------------------------------|---------------------------------|
| `/jobs`               | `JobListComponent`            | View all job postings           |
| `/jobs/new`           | `JobFormComponent`            | Post a new job                  |
| `/jobs/edit/:id`      | `JobFormComponent`            | Edit an existing job            |
| `/jobs/:id`           | `JobDetailsComponent`         | View job details                |
| `/jobs/:id`           | `JobFormComponent`            | Delete an existing job          |
| `/jobs/:id/apply`     | `JobApplicationFormComponent` | Apply for the job               |
| `/applications`       | `JobApplicationListComponent` | Display all application listings|
| `/applications/:id`   | `JobApplicationListComponent` | Display specific application    |



### 🎨 UI & Styling

- Built using **Angular Material** components
- Gradient card styling for job listings
- Responsive layout
- Form validation and success/error feedback

### 📦 Required Packages

Make sure you have the following installed:

```bash
npm install
ng add @angular/material
```

## 📖 Job Portal Backend API (Node.js + Express + MySQL)

### 🔹 Base URL

```
http://localhost:5000/api
```

### ✅ JOBS

#### 📘 GET `/jobs`
Fetch all job listings.

**Response:**
```json
[
  {
    "id": 1,
    "job_title": "Frontend Developer",
    "company_name": "TechCorp",
    "location": "Remote",
    "job_type": "Full-time",
    "salary_range": "60000-80000",
    "job_description": "Looking for skilled React developer.",
    "application_deadline": "2025-06-01"
  }
]
```

#### 📘 GET `/jobs/:id`
Fetch a specific job by ID.

**Response:**
```json
{
  "id": 1,
  "job_title": "Frontend Developer",
  "company_name": "TechCorp",
  "location": "Remote",
  "job_type": "Full-time",
  "salary_range": "60000-80000",
  "job_description": "Looking for skilled React developer.",
  "application_deadline": "2025-06-01"
}
```

#### 📘 POST `/jobs`
Create a new job.

**Request Body:**
```json
{
  "job_title": "Backend Developer",
  "company_name": "CodeInc",
  "location": "Bangalore",
  "job_type": "Part-time",
  "salary_range": "40000-60000",
  "job_description": "Experience with Node.js and MySQL",
  "application_deadline": "2025-07-01"
}
```

**Response:**
```json
{
  "message": "Job created successfully",
  "jobId": 2
}
```

#### 📘 PUT `/jobs/:id`
Update a job by ID.

**Request Body:** (same as POST)

**Response:**
```json
{
  "message": "Job updated successfully"
}
```

#### 📘 DELETE `/jobs/:id`
Delete a job by ID.

**Response:**
```json
{
  "message": "Job deleted successfully"
}
```

### ✅ APPLICATIONS

#### 📘 POST `/jobs/:id/apply`
Apply to a job.

**Request Body:**
```json
{
  "applicant_name": "John Doe",
  "email": "john@example.com"
}
```

**Response:**
```json
{
  "message": "Application submitted successfully",
  "applicationId": 1
}
```

#### 📘 GET `/applications`
List all job applications.

**Response:**
```json
[
  {
    "id": 1,
    "job_id": 2,
    "applicant_name": "John Doe",
    "email": "john@example.com",
    "applied_at": "2025-04-09T10:30:00.000Z"
  }
]
```

#### 📘 GET `/applications/:id`
Fetch one application by ID.

**Response:**
```json
{
  "id": 1,
  "job_id": 2,
  "applicant_name": "John Doe",
  "email": "john@example.com",
  "applied_at": "2025-04-09T10:30:00.000Z"
}
```

### ⚠️ Error Responses

#### 400 – Validation Error
```json
{
  "errors": [
    {
      "msg": "Job title is required",
      "param": "job_title",
      "location": "body"
    }
  ]
}
```

#### 404 – Not Found
```json
{
  "error": "Job not found"
}
```

#### 500 – Internal Server Error
```json
{
  "error": "Failed to fetch job"
}
```

---

## ⚙️ Environment Variables

Create a `.env` file in the `backend/` directory and update it with your **MySQL** connection details:

```env
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=job_portal
```

📌 **Note:** Make sure to restart the server after any changes to the `.env` file.

---


