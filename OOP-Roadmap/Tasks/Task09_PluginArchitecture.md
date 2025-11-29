# Task 9 — Plugin Architecture

**Description:**  
Create an abstract `Plugin` class and implement `LoggerPlugin` and `AnalyticsPlugin`. Allow dynamic loading of multiple plugins and executing them.

**Requirements / Steps:**

1. Define an abstract class `Plugin` with a method `execute()`.
2. Implement at least two plugins:
   - `LoggerPlugin` — logs a message to the console.
   - `AnalyticsPlugin` — prints analytics data or simulates analytics processing.
3. Create an `Application` class that:
   - Maintains a **list of plugins**.
   - Has a method `register(Plugin plugin)` to add new plugins dynamically.
   - Has a method `run()` that executes all registered plugins in order.
4. In `main()`, register multiple plugins and call `run()` to see the dynamic execution.

**References:**  
[Open/Closed Principle & Polymorphism](https://medium.com/@shouaibmoha247/solid-principles-in-dart-part-02-open-closed-principle-db6b7b7f0bff)

**Hints:**

- Store plugins in a list and execute methods polymorphically
- Ensure new plugins can be added without modifying existing code
