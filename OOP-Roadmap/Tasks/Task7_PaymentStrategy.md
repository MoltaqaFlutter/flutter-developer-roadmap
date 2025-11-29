# Task 7 — Payment Strategy Pattern

**Description:**  
Implement a `PaymentStrategy` interface and create classes `PayPal`, `CreditCard`, and `Cash` that implement it. Create a `Checkout` class to process payments using the selected strategy.

**References:**  
[Strategy Pattern — Refactoring Guru](https://refactoring.guru/design-patterns/strategy)
[Strategy Pattern — Mohamed El-Mahdy](https://www.youtube.com/watch?v=MdB6zKDeb44&list=PLsV97AQt78NTrqUAZM562JbR3ljX19JFR&index=4)

**Hints:**

- Use composition to allow changing payment strategy at runtime
- Implement a method in `Checkout` to execute the selected payment
