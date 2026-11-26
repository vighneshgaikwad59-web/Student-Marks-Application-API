# Student Marks & Application API

A beginner-friendly REST API project built using **Python, FastAPI, and Pydantic**. This project manages student application details and validates submitted examination marks through GET and POST endpoints.

## Features

- Retrieve student application details using GET.
- Submit student marks using POST.
- Validate student names.
- Prevent negative marks.
- Restrict marks to a maximum of 100.
- Handle errors using HTTPException.
- Validate request data using Pydantic.

## Technologies Used

- Python
- FastAPI
- Pydantic
- Uvicorn
- REST API

## Project Structure

```text
Student-Marks-API/
│
├── main.py
├── requirements.txt
├── README.md
└── .gitignore
```

## Installation

**1. Clone the repository**

```bash
git clone YOUR_REPOSITORY_URL
```

**2. Navigate to the project folder**

```bash
cd Student-Marks-API
```

**3. Install dependencies**

```bash
python -m pip install -r requirements.txt
```

**4. Run the application**

```bash
python -m uvicorn main:app --reload
```

## API Endpoints

### 1. GET – Student Application

**Endpoint:**

```text
GET /application/{student_id}
```

Example:

```text
http://127.0.0.1:8000/application/SOO1
```

Sample Response:

```json
{
    "NAME": "RIYA",
    "WORK": "OCCUPIED"
}
```

### 2. POST – Submit Student Marks

**Endpoint:**

```text
POST /submit-marks
```

Sample Request:

```json
{
    "student": "RIYA",
    "marks": 85,
    "subject": "Bioinformatics"
}
```

Sample Response:

```json
{
    "message": "Marks submitted successfully",
    "student": "RIYA",
    "marks": 85,
    "subject": "Bioinformatics"
}
```

## Validation Rules

| Condition | Response |
|---|---|
| Student not found | 404 Error |
| Marks below 0 | 400 Error |
| Marks above 100 | 400 Error |
| Valid student and marks | Success |

## API Documentation

After running the application, open:

- Swagger UI: http://127.0.0.1:8000/docs
- ReDoc: http://127.0.0.1:8000/redoc

## Learning Outcomes

Through this project, I practiced:

- Creating REST APIs using FastAPI.
- Understanding GET and POST methods.
- Using Pydantic models for data validation.
- Handling HTTP errors.
- Testing APIs using Swagger UI.

## Future Improvements

- Add more student records.
- Store student marks in a database.
- Create an API to retrieve submitted marks.
- Implement PUT and DELETE endpoints.
- Add student registration functionality.


