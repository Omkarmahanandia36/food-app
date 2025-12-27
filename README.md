# Recipe Management System

A full-stack **Recipe Management System** that provides **personalized recipe recommendations** based on user preferences such as diet type, allergies, and disliked ingredients.  
The system integrates with a **free external recipe API** and stores user data securely using **MySQL**.

---

## Features

### Authentication
- User **Sign Up** and **Login**
- Secure authentication using **JWT (JSON Web Token)**
- Protected routes for authenticated users only

### User Preferences
- Select **diet type** (Vegetarian / Non-Vegetarian)
- Choose **cooking skill level**
- Specify **allergies** and **disliked ingredients**
- Preferences stored in a separate database table linked to users

### Recipe Listing
- Fetches live recipes from **TheMealDB API**
- Displays recipes as responsive cards
- Search recipes by name
- Filter recipes by:
  - Vegetarian
  - Non-Vegetarian (mapped internally)

###  Recipe Details
- Full-screen hero image
- Ingredients with measurements
- Step-by-step cooking instructions
- Category and cuisine information

### UI & UX
- Fully responsive design
- Clean modern layout
- Desktop-first hero image design
- Optimized for readability

---

## Tech Stack

### Frontend
- HTML5
- CSS3
- JavaScript (ES Modules)
- Live Server

### Backend
- Node.js
- Express.js
- MySQL
- JWT Authentication
- dotenv
- CORS

### External API
- **TheMealDB** (Free public API)

##  Authentication Flow

1. User signs up or logs in
2. Backend issues a JWT token
3. Token is stored in `localStorage`
4. Protected routes require `Authorization: Bearer <token>`
5. On logout:
   - Token is removed
   - All cached data is cleared
   - User is redirected to login page

---

## Database Design

### `users`
- `id` (PK)
- `name`
- `email`
- `password` (hashed)

### `preferences`
- `id` (PK)
- `user_id` (FK → users.id, UNIQUE)
- `diet_type`
- `cooking_level`
- `allergies`
- `disliked_ingredients`

### `reviews`
- `id` (PK)
- `user_id` (FK → users.id)
- `recipe_id`
- `rating`
- `comment`
- `created_at`
- UNIQUE (`user_id`, `recipe_id`)

---

## 📁 Frontend Folder Structure



