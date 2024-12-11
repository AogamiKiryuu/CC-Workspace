# API Documentation: Ingrevia Test

## Table of Contents
- [Overview](#overview)
- [Endpoints](#endpoints)
  - [Auth](#auth)
  - [Home](#home)
  - [User](#user)
  - [Recipes](#recipes)
  - [Favorites](#favorites)

---

## Overview
This API provides functionality for authentication, user management, recipe management, and favorites. Below is a list of all the endpoints grouped by their respective categories.

Base URL: `http://localhost:5000`

---

## Endpoints

### Auth

#### 1. Register
- **Method**: `POST`
- **URL**: `/auth/register`
- **Request Body**:
  ```json
  {
    "email": "user@example.com",
    "name": "test",
    "password": "userpassword"
  }
  ```
- **Description**: Registers a new user.

#### 2. Login with Email
- **Method**: `POST`
- **URL**: `/auth/login/email`
- **Request Body**:
  ```json
  {
    "email": "user@example.com",
    "password": "userpassword"
  }
  ```
- **Description**: Logs in a user with their email and password.

#### 3. Login with Google
- **Method**: `POST`
- **URL**: `/auth/login/google`
- **Description**: Logs in a user via Google authentication.

#### 4. Forgot Password
- **Method**: `POST`
- **URL**: `/auth/forgot-password`
- **Request Body**:
  ```json
  {
    "email": "user@example.com"
  }
  ```
- **Description**: Initiates password reset for a user.

#### 5. Logout
- **Method**: `POST`
- **URL**: `/auth/logout`
- **Description**: Logs out the user.

---

### Home

#### 1. Recommendations
- **Method**: `GET`
- **URL**: `/recommendations`
- **Description**: Fetches recommendations for the user.

#### 2. Search
- **Method**: `GET`
- **URL**: `/home/search?query={query}`
- **Query Parameters**:
  - `query`: Search term (e.g., `pastasalad`)
- **Description**: Searches for recipes based on a query.

#### 3. Categories
- **Method**: `GET`
- **URL**: `/home/categories`
- **Description**: Fetches recipe categories.

---

### User

#### 1. Profile
- **Method**: `GET`
- **URL**: `/user/profile`
- **Description**: Fetches user profile details.

#### 2. Update Profile
- **Method**: `PUT`
- **URL**: `/user/profile`
- **Description**: Updates the user's profile.

#### 3. Theme
- **Method**: `GET`
- **URL**: `/user/theme`
- **Description**: Fetches the user's theme preferences.

#### 4. Photo Profile
- **Method**: `POST`
- **URL**: `/user/profile-pic`
- **Description**: Uploads a new profile picture for the user.

#### 5. About
- **Method**: `GET`
- **URL**: `/user/about`
- **Description**: Fetches information about the user.

---

### Recipes

#### 1. Recipe by ID
- **Method**: `GET`
- **URL**: `/recipes/{recipe_id}`
- **Description**: Fetches details of a recipe by its ID.

---

### Favorites

#### 1. Get Favorite Recipes
- **Method**: `GET`
- **URL**: `/favorites`
- **Description**: Fetches a list of the user's favorite recipes.

#### 2. Add Recipe to Favorites
- **Method**: `POST`
- **URL**: `/favorites/{id}`
- **Description**: Adds a recipe to the user's list of favorites.

#### 3. Remove Recipe from Favorites
- **Method**: `DELETE`
- **URL**: `/favorites/{id}`
- **Description**: Removes a recipe from the user's favorites.

#### 4. Get Categories of Favorite Recipes
- **Method**: `GET`
- **URL**: `/favorites/categories`
- **Description**: Fetches categories from the user's favorite recipes.

---

## Notes
- Replace `{id}` and `{recipe_id}` with the actual values when making requests.
- This API assumes a running server on `localhost:5000`. Adjust the base URL for deployment environments.
