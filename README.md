[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/iG82Gnyy)

# Campground Booking API

> **Project #2 — SW Dev Practice**
> Backend REST API built with **Node.js / Express / MongoDB Atlas**

---

## Project Requirements

| #  | Requirement |
|----|-------------|
| 1  | Register with name, telephone number, email, and password |
| 2  | Login with email + password; logout |
| 3  | Book up to **3 nights** at a preferred campground (specify date) |
| 4  | Registered user: view own bookings |
| 5  | Registered user: edit own bookings |
| 6  | Registered user: delete own bookings |
| 7  | Admin: view **any** booking |
| 8  | Admin: edit **any** booking |
| 9  | Admin: delete **any** booking |

---

## Tech Stack
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB Atlas (Mongoose ODM)
- **Auth**: JSON Web Tokens (JWT) + bcryptjs
- **Test tool**: Postman

---

## Getting Started

```bash
# 1. Install dependencies
npm install

# 2. Set up environment variables
cp config/config.env.example config/config.env
# Fill in MONGO_URI, JWT_SECRET, JWT_EXPIRE, JWT_COOKIE_EXPIRE

# 3. Start the server (development)
npm run dev

# 4. Start the server (production)
npm start
```

---

## API Endpoints

### Auth — `/api/v1/auth`
| Method | Path       | Access  | Description                     |
|--------|------------|---------|----------------------------------|
| POST   | /register  | Public  | Register a new user              |
| POST   | /login     | Public  | Login and receive JWT token      |
| GET    | /logout    | Private | Logout (clear cookie)            |
| GET    | /me        | Private | Get logged-in user profile       |

### Campgrounds — `/api/v1/campgrounds`
| Method | Path   | Access       | Description              |
|--------|--------|--------------|--------------------------|
| GET    | /      | Public       | Get all campgrounds      |
| GET    | /:id   | Public       | Get single campground    |
| POST   | /      | Admin only   | Create a campground      |
| PUT    | /:id   | Admin only   | Update a campground      |
| DELETE | /:id   | Admin only   | Delete a campground      |

### Bookings — `/api/v1/bookings` or `/api/v1/campgrounds/:campgroundId/bookings`
| Method | Path   | Access        | Description              |
|--------|--------|---------------|--------------------------|
| GET    | /      | Private       | Get bookings (own/all)   |
| GET    | /:id   | Private       | Get single booking       |
| POST   | /      | Private       | Create a booking         |
| PUT    | /:id   | Private       | Update a booking         |
| DELETE | /:id   | Private       | Delete a booking         |
