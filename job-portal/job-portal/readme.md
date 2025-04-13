## 📘 Job Portal API Documentation

### 🔹 Base URL
```
http://localhost:5000/api
```

---

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

---

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

---

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

---

#### 📘 PUT `/jobs/:id`
Update a job by ID.

**Request Body:**
*(Same as POST)*

**Response:**
```json
{
  "message": "Job updated successfully"
}
```

---

#### 📘 DELETE `/jobs/:id`
Delete a job by ID.

**Response:**
```json
{
  "message": "Job deleted successfully"
}
```

---

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

---

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

---

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

---

### ⚠️ Error Responses

#### 400 – Validation error
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

#### 404 – Not found
```json
{
  "error": "Job not found"
}
```

#### 500 – Internal server/database error
```json
{
  "error": "Failed to fetch job"
}
```

---

✅ **Done!** You can add this file to your project root as `API_DOC.md`

