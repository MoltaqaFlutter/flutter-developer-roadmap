# 🛒 Feature 4: Cart & Orders

**Goal**: The heart of E-Commerce. Handling money and inventory.

---

## 🔄 The User Flow

### 1. The Cart (Persistent)
We don't just store the cart in the browser (Local Storage). We store it in the **Database** so the user sees the same cart on their Phone and Laptop.
1.  **Add to Cart**:
    -   User sends `productId` + `qty`.
    -   Server checks if product exists.
    -   Server adds to user's `cart` array in DB.
2.  **Sync**: If user adds same item again, **increment quantity**, don't duplicate item.

### 2. Creating an Order
1.  **Checkout**: User confirms items.
2.  **Order Creation**:
    -   Server copies items from `Cart` to a new `Order` record.
    -   **CRITICAL**: Server calculates `Total Price` on backend (Never trust price sent from frontend).
3.  **Payment Status**:
    -   Initially `isPaid: false`.
    -   After payment gateway confirms, set `isPaid: true`.

---

## ✅ Internship Tasks

### 1. Inventory Deduction
-   **Context**: If I have 10 iPhones and someone buys 1, I should have 9.
-   **Task**:
    1.  When an Order is created (or Paid), iterate through the order items.
    2.  Find each Product in DB.
    3.  `product.countInStock = product.countInStock - item.qty`.
    4.  Save Product.

### 2. "My Orders" History
-   **Task**: Create an endpoint that shows a user their past orders.
-   **Details**:
    -   Endpoint: `GET /api/orders/myorders`
    -   Filter: `Order.find({ user: req.user._id })`
    -   Sort: Newest first.

### 3. Admin Order Dashboard
-   **Task**: Give Admin a view of all sales.
-   **Details**:
    -   Endpoint: `GET /api/orders` (Private + Admin).
    -   Calculate "Total Sales" (Sum of all order prices).
