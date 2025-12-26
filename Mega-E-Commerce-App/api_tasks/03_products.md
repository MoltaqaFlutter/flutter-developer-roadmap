# 🛍️ Feature 3: Products & Catalog

**Goal**: Create a rich, searchable marketplace.

---

## 🔄 The User Flow

### 1. Admin Management (The Seller)
1.  **Create Product**:
    -   Admin sends Name, Price, Description, CountInStock, and **Images**.
    -   Server saves to DB.
2.  **Manage Stock**:
    -   Admin can update `countInStock`.

### 2. User Browsing (The Buyer)
1.  **List Products**: User sees a grid of products.
2.  **Search**: User types "iPhone" -> Server checks if name contains "iPhone".
3.  **Filter**: User selects "Electronics" category -> Server filters results.

---

## ✅ Internship Tasks

### 1. Multi-Image Upload
-   **Context**: Products usually have more than one image (Front, Back, Side).
-   **Task**:
    1.  Update `productController.js` -> `createProduct` to handle `req.files` (plural).
    2.  Allow uploading up to 5 images.
    3.  Save all URLs to an `images` array in the Product Schema.

### 2. Advanced Filtering
-   **Context**: API currently supports basic pagination and keyword search.
-   **Task**: Add more filters to `getProducts`.
    -   `?minPrice=100&maxPrice=500`
    -   `?category=Electronics`
    -   `?rating=4` (Show products with average rating >= 4)

### 3. Product Reviews Logic
-   **Task**: Prevent Review Spam.
    -   Ensure a user can only review a product **once**.
    -   Ensure a user can only review a product they have **actually purchased** (Advanced: check Orders history).
