#  Mugisha Bookstore API

A RESTful API for managing books in Mugisha's bookstore in Kigali. Built with Node.js, Express, and MongoDB following the MVC architecture.

---

##  Project Structure

```
mugisha-bookstore/
├── config/
│   └── db.js               # MongoDB connection
├── controllers/
│   └── bookController.js   # Business logic
├── models/
│   └── Book.js             # Book schema
├── routes/
│   └── bookRoutes.js       # API routes
├── .env                    # Environment variables
└── server.js               # Entry point
```

---

## ⚙️ Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [MongoDB](https://www.mongodb.com/) running locally
- [Postman](https://www.postman.com/) or Thunder Client for testing

---

##  Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/mugisha-bookstore.git
cd mugisha-bookstore
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Create a `.env` file in the root of the project:

```env
PORT=3000
MONGO_URI=mongodb://localhost:27017/mugisha_bookstore
```

### 4. Start the server

```bash
# Development (with auto-restart)
npm run dev

# Production
npm start
```

You should see:

```
MongoDB connected
Server running on port 3000
```

---

##  Dependencies

| Package    | Purpose                        |
|------------|--------------------------------|
| express    | Web framework                  |
| mongoose   | MongoDB object modeling        |
| dotenv     | Environment variable loader    |
| nodemon    | Auto-restart in development    |

---

## 📖 Book Model

| Field  | Type   | Required |
|--------|--------|----------|
| title  | String |  Yes   |
| author | String |  Yes   |
| price  | Number |  Yes   |

---

## 🔌 API Endpoints

Base URL: `http://localhost:3000/api/books`

### Create a book

```
POST /api/books
```

**Request body:**

```json
{
  "title": "Things Fall Apart",
  "author": "Chinua Achebe",
  "price": 15
}
```

**Response `201`:**

```json
{
  "_id": "685a1c3f2e4b7a001d9f8c21",
  "title": "Things Fall Apart",
  "author": "Chinua Achebe",
  "price": 15,
  "__v": 0
}
```

---

### Get all books

```
GET /api/books
```

**Response `200`:**

```json
[
  {
    "_id": "685a1c3f2e4b7a001d9f8c21",
    "title": "Things Fall Apart",
    "author": "Chinua Achebe",
    "price": 15
  }
]
```

---

### Get one book by ID

```
GET /api/books/:id
```

**Response `200`:**

```json
{
  "_id": "685a1c3f2e4b7a001d9f8c21",
  "title": "Things Fall Apart",
  "author": "Chinua Achebe",
  "price": 15
}
```

**Response `404` (not found):**

```json
{ "error": "Book not found" }
```

---

### Update a book

```
PUT /api/books/:id
```

**Request body (any field to update):**

```json
{
  "price": 20
}
```

**Response `200`:**

```json
{
  "_id": "685a1c3f2e4b7a001d9f8c21",
  "title": "Things Fall Apart",
  "author": "Chinua Achebe",
  "price": 20
}
```

---

### Delete a book

```
DELETE /api/books/:id
```

**Response `200`:**

```json
{ "message": "Book deleted successfully" }
```

---

##  MVC Flow

```
Request → routes/bookRoutes.js
               ↓
     controllers/bookController.js
               ↓
           models/Book.js  ←→  MongoDB
               ↓
            Response
```

---

##  Scripts

```bash
npm run dev    # Start with nodemon (development)
npm start      # Start with node (production)
```

---

##  Author

Built by **Moise** for Mugisha's Bookstore — Kigali, Rwanda.
