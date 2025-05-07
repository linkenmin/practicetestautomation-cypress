# practicetestautomation-cypress

This project demonstrates end-to-end browser-based UI testing using **JavaScript**, **Cypress**, and **Mocha/Chai** for the practice login site: https://practicetestautomation.com/practice-test-login/. It provides a simple, maintainable test framework with built-in retry/auto-wait, screenshots, video recording, and CLI/GUI runners.

## Design Philosophy

1. **Centralized Test Setup**  
   - Use `beforeEach()` to visit the login page before every test  
   - Encapsulate common actions (e.g. `login()`) in helper functions for DRY code

2. **Clear, Focused Test Cases**  
   - One `it()` per scenario: successful login, invalid username, invalid password  
   - Descriptive titles so failures are immediately clear in reports

3. **Built-in Cypress Features**  
   - **Time Travel**: automatic DOM snapshots for every command in the Cypress Test Runner  
   - **Auto-waiting & Retry**: built-in waits for commands and assertions  
   - **Screenshots & Video**: automatic capture on failure, configurable in headless runs

4. **Flexible Execution Modes**  
   - **GUI** for interactive development & debugging  
   - **Headless CLI** for CI pipelines, with full reports & artifacts generation

---

## Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/linkenmin/practicetestautomation-cypress.git
   cd practicetestautomation-cypress
````

2. **Initialize & install dependencies**

   ```bash
   npm install
   ```

3. **Open Cypress Test Runner**

   ```bash
   npx cypress open
   ```

---

## Running Tests

* **Interactive GUI**

  ```bash
  npx cypress open
  ```

  Select `login.cy.js` to run tests step by step with time-travel snapshots.

* **Headless CLI**

  ```bash
  npx cypress run --spec "cypress/e2e/login.cy.js"
  ```

---

## Project Structure

```
├── cypress/
│   ├── e2e/
│   │   └── login.cy.js          # Positive & negative login test cases
│   ├── fixtures/
│   ├── support/
│   │   ├── commands.js
│   │   └── e2e.js
└── cypress.config.js            # Cypress configuration (reporter, baseUrl, etc.)
```
