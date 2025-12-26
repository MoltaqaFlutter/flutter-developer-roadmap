# 📡 Mega Ecommerce Intern App Backend

**Made by Eng. Magdy Ebrahim Ali**  
**Contact**: magdyerahim155@gmail.com

---

## 🌐 API Information

-   **Base URL (Production)**: `https://mega155-ecommerce-app-backend.vercel.app`
-   **Local Development**: `http://localhost:5000`

### 📚 Documentation Links
1.  **Swagger UI (Visual Documentation)**:  
    [https://mega155-ecommerce-app-backend.vercel.app/api-docs](https://mega155-ecommerce-app-backend.vercel.app/api-docs)
    *Use this to visually explore all endpoints, schemas, and try out requests directly in the browser.*

2.  **Postman Collection**:  
    [Postman Link](https://mega66-1484.postman.co/workspace/Mega-Workspace~9b99e0e5-50c3-45ae-813f-9881b120449c/collection/15518880-e33c5b61-bd85-436a-9897-be13da06e1df?action=share&creator=15518880&active-environment=15518880-48d8a64b-2258-4ccc-b728-01a9ee0da6b6)
    *Import this file into Postman to have a ready-to-use testing suite for all endpoints.*

---

## 🛠️ How to Connect (Headers)

To make requests to this API (via Postman, Mobile App, or Web App), you must use the correct headers.

### 1. General Requests (JSON)
For most requests (Login, Get Products, Create Order), use **JSON**:
```http
Content-Type: application/json
Accept: application/json
```

### 2. Login Request (Special Case)
The `/api/auth/login` endpoint supports `multipart/form-data` for compatibility, but `application/json` is the standard.
*   **Body**: `email`, `password`

### 3. File Uploads (Images)
When uploading files (Signup with Avatar, Create Product), you **MUST** use `multipart/form-data`.
*   **Do NOT** set `Content-Type` manually in your code; let your HTTP client (Postman/Axios/Flutter/Dio) set it automatically so it includes the "boundary".
*   **Body**: Fields (e.g., `name`) + Files (e.g., `avatar`).

### 4. Authenticated Requests (Private)
For private routes (User Profile, Place Order), you must include the **JWT Token** received after login.
```http
Authorization: Bearer <YOUR_TOKEN_HERE>
```

---

## 📂 Project Structure for Interns
The tasks are divided into feature-based modules in this folder:
-   `01_authentication.md`: Signup, Login, Email Verification.
-   `02_user_profile.md`: Managing User Identity.
-   `03_products.md`: Catalog and Searching.
-   `04_cart_and_orders.md`: Shopping Logic.
-   `05_payments.md`: Payment Integration.
