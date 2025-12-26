# 🔐 Feature 1: Authentication & Security

**Goal**: Build a secure gatekeeper for the application. Ensure that only "Real" users can access the system.

---

## 🔄 The User Flow

### 1. Sign Up & Verification (The "Verified User" Case)
This is the most critical part of the flow.
1.  **User Enters Data**: Name, Email, Password, Avatar.
2.  **System Checks**:
    -   Is email already used? -> Error.
    -   Is password strong enough?
3.  **Account Creation**:
    -   Server creates user in Database.
    -   **CRITICAL**: `isVerified` is set to `false`.
    -   Server generates a random 4-6 digit code (e.g., `4821`).
    -   Server sends this code to the User's Email.
4.  **Verification**:
    -   User checks email -> Enters Code in App.
    -   Server matches code -> Sets `isVerified` to `true`.
    -   *Only now is the user considered a "Real" user.*

### 2. Login
1.  User enters Email & Password.
2.  Server checks:
    -   Does user exist?
    -   Does password match?
3.  Server issues a **JWT Token**. This token is the "Key" for all future requests.

---

## ✅ Internship Tasks

### 1. Email Service Integration (Nodemailer)
-   **Context**: Currently, the app just logs the verification code to the console (Fake Email).
-   **Task**: Implement real email sending.
-   **Steps**:
    1.  Install `nodemailer`.
    2.  Create a Gmail account (or use SendGrid/Mailgun free tier).
    3.  Configure `SMTP` settings in `.env`.
    4.  Update `authController.js` -> `sendVerificationCode` to send the actual email.

### 2. Protect Routes for Verified Users
-   **Context**: Some features (like Buying items) should only be for `isVerified: true` users.
-   **Task**:
    1.  Create a new middleware `verifiedOnly` in `src/middleware/auth.js`.
    2.  Check if `req.user.isVerified` is true.
    3.  If false, return `403 Forbidden` ("Please verify your email first").
    4.  Apply this middleware to the `Place Order` route.

### 3. Password Reset Flow
-   **Task**: Implement the "Forgot Password" flow.
    1.  Endpoint `POST /api/auth/forgot-password`: User sends email -> System sends Code.
    2.  Endpoint `POST /api/auth/reset-password`: User sends (Email + Code + NewPassword).
    3.  System updates password.
