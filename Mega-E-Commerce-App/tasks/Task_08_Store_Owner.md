# Task 3: Store Owner

## 🎯 Goal
Make user being store owner can manage its products.

## 📝 Tasks

### 1. Make Cart
- **Api**
you can find api services here
  [Swager_API](https://mega155-ecommerce-app-backend.vercel.app/api-docs/#/Products)

- **Task**:
  - In menu add being store owner tile shown in figma ui.
  - On tap (being store owner tile) opens send store request to admin page.
  - Make send being store page design and logic.
  - [Senario] ::: 
    - User make request to admin to being as store owner .
    - Reuquest sends to admin that has ablity to accept or reject the request [Api](https://mega155-ecommerce-app-backend.vercel.app/api-docs/#/Requests%20-%20Admin).
    - On admin action like accept or reject user recive notification for the admin action.
    - Case admin reject the requets he attacthed the reason and user can make request flow again.
    - Case admin approve request :
      - In menu being store tile is being mange store tile.
      - Can open its store products and preview to him with ablity to add new products ,delete and edit its own products.
      - Make add && product details && delete && edit pages.