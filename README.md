# DecodeLabs Project 2 — Backend API Development

A simple RESTful API built with **Node.js + Express** covering all key requirements from the DecodeLabs Full Stack Internship spec.

---

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Data Store:** In-memory (Array — no database needed)

---

## How to Run

```bash
# 1. Install dependencies
npm install

# 2. Start the server
node server.js
```

Server runs at: `http://localhost:3000`

---

## API Endpoints

### GET `/`
Returns API info and available endpoints.

---

### GET `/users`
Returns all users.

**Response `200`:**
```json
{
  "status": "success",
  "count": 2,
  "data": [
    { "id": 1, "name": "Alisha Yousaf", "email": "alisha@example.com", "role": "admin" }
  ]
}
```

---

### GET `/users/:id`
Returns a single user by ID.

**Response `200`:** User object  
**Response `400`:** ID is not a number  
**Response `404`:** User not found  

---

### GET `/users/search?name=&role=`
Search users by name or role.

**Example:** `/users/search?role=admin`

**Response `200`:** Matching users  
**Response `400`:** No query params provided  
**Response `404`:** No matches found  

---

### POST `/users`
Create a new user.

**Request Body:**
```json
{
  "name": "Zara Ahmed",
  "email": "zara@example.com",
  "role": "user"
}
```

**Validations:**
- `name` — required, min 2 characters
- `email` — required, valid format
- `role` — optional; defaults to `"user"` if not provided or invalid

**Response `201`:** Created user  
**Response `400`:** Validation error  
**Response `409`:** Email already exists  

---

## HTTP Status Codes Used

| Code | Meaning         |
|------|-----------------|
| 200  | OK              |
| 201  | Created         |
| 400  | Bad Request     |
| 404  | Not Found       |
| 409  | Conflict        |
| 500  | Internal Error  |

---

*DecodeLabs Batch 2026 — Full Stack Development Internship*


