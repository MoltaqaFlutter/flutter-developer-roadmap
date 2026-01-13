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
