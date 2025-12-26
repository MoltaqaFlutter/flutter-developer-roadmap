# 👤 Feature 2: User Profile & Settings

**Goal**: Allow users to manage their identity and ensure data integrity.

---

## 🔄 The User Flow

### 1. Profile Management
1.  **Get Profile**: User requests own data.
2.  **Update Avatar**:
    -   User uploads a new image file.
    -   **Cloudinary**: The server sends this file to Cloudinary.
    -   **DB**: The server saves the *URL* returned by Cloudinary to the database.

### 2. Update Email (Secure Flow)
Changing an email is dangerous (someone could hijack an account).
1.  **Request Update**:
    -   User inputs `newEmail`.
    -   Server checks if `newEmail` is already taken.
    -   Server sends a Verification Code to the **NEW** email.
2.  **Verify Update**:
    -   User gets code from new inbox.
    -   User sends Code back to server.
    -   Server updates `user.email` to `newEmail`.

---

## ✅ Internship Tasks

### 1. Cloudinary Integration
-   **Context**: We need persistent image storage.
-   **Task**:
    1.  Sign up for [Cloudinary](https://cloudinary.com).
    2.  Get `Cloud Name`, `API Key`, `API Secret`.
    3.  Add to `.env` file.
    4.  Test upload: Upload an avatar and check if it appears in Cloudinary Dashboard.

### 2. Prevent Duplicate Avion
-   **Task**: Ensure a user cannot upload an avatar that is not an image (e.g. PDF or EXE).
-   **Steps**:
    1.  Check `multer` configuration.
    2.  Add a file filter to only allow `image/jpeg`, `image/png`, `image/webp`.

### 3. "Pending Email" State
-   **Task**: Improve the Email Update flow.
-   **Steps**:
    1.  When user requests email update, save `newEmail` in a temporary field `pendingEmail` in the Database (you may need to add this property to the User Schema).
    2.  Only move `pendingEmail` to `email` after the code is verified.
