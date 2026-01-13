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

### 3. Password Reset Flow
-   **Task**: Implement the "Forgot Password" flow.
    1.  Endpoint `POST /api/auth/forgot-password`: User sends email -> System sends Code.
    2.  Endpoint `POST /api/auth/reset-password`: User sends (Email + Code + NewPassword).
    3.  System updates password.
