# 💳 Feature 5: Real Payments (Integration)

**Goal**: Move from "Mock" payments to Real Money using Stripe.

---

## 🔄 The User Flow

### The Payment Intent Flow (Standard Modern Stripe)
1.  **Initiate**: User clicks "Pay".
2.  **Handshake**:
    -   Frontend asks Backend: "I want to pay for Order #123".
    -   Backend calculates price -> Calls Stripe API -> Creates **PaymentIntent**.
    -   Backend sends `clientSecret` to Frontend.
3.  **Processing**:
    -   Frontend uses `Stripe.js` + `clientSecret` to show Credit Card form.
    -   User pays -> Stripe processes it directly (Secure).
4.  **Confirmation**:
    -   Stripe tells Frontend: "Success".
    -   **Webhook**: Stripe servers tell *Our* User Server: "Payment Succeeded" (This is how we verify).

---

## ✅ Internship Tasks

### 1. Stripe Setup
-   **Task**:
    1.  Create Stripe Developer Account (Test Mode).
    2.  Get `STRIPE_SECRET_KEY` and `STRIPE_PUBLISHABLE_KEY`.
    3.  Install `stripe` npm package.

### 2. Create Payment Endpoint
-   **Task**: Implement `POST /api/orders/:id/pay`.
-   **Logic**:
    1.  Find Order.
    2.  Check if already paid.
    3.  Create Stripe Payment Intent with `amount = order.totalPrice`.
    4.  Return `clientSecret`.

### 3. Handle Webhook (Advanced)
-   **Task**: Build a webhook endpoint to listen for Stripe events.
-   **Why**: If the user closes the browser *after* paying but *before* the frontend tells us, we still need to know they paid.
-   **Endpoint**: `POST /api/config/stripe-webhook`.
