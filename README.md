# QA Sauce Demo Project

## 📌 Project Overview

This is a manual QA testing project for the e-commerce demo web application **Sauce Demo**.

The project covers the main user flows, including authentication, product catalog, shopping cart, checkout process, navigation, session handling, and basic UI/usability checks.

It demonstrates practical skills in test analysis, test design, test case creation, bug reporting, test documentation, and understanding of SDLC, STLC, and QA processes.

## 🧪 Scope of Testing
The scope of testing covers the main user flow and core functionality of the Sauce Demo web application, including authentication, product browsing, cart management, checkout process, navigation, session behavior, and basic UI/usability checks.

The tested areas include:

- User authentication
  Login with valid users, invalid credentials, locked out user behavior, required field validation, password masking, error messages, logout, re-authentication, and session handling.

- Product catalog
  Product list display, product names, descriptions, prices, images, sorting options, product details navigation, add/remove product behavior, cart badge updates, and user-specific product page behavior.

- Shopping cart
  Cart page navigation, selected product display, item removal, cart badge updates, empty cart state, cart persistence after refresh, cart behavior for different users, and direct access/session restrictions.

- Checkout process
  Checkout information form validation, required fields, valid and invalid input handling, checkout overview data accuracy, item total, tax and total consistency, order completion, cancel/back navigation, cart reset after purchase, and checkout behavior for different user profiles.

- Navigation and menu functionality
  Hamburger menu open/close behavior, All Items navigation, About link redirection, Logout, Reset App State, browser back behavior, and navigation between Products, Cart, Checkout, and Product Details pages.

- Session and access control
  Direct URL access restrictions for protected pages, behavior after logout, browser back button after logout, manual storage/session clearance, and access attempts without an active session.

- User-specific behavior
  Verification of application behavior for standard_user, problem_user, performance_glitch_user, error_user, and visual_user where relevant to the tested functionality.

- Basic UI and usability checks
  Visibility, readability, layout alignment, button clarity, error message visibility, cart badge visibility, responsive behavior on different screen sizes, and visual consistency for key pages.

## 🛠 Testing Types Used
- Functional testing
- Smoke testing
- Exploratory testing for user-specific behavior and edge cases
- Performance testing
- Security testing
- Usability testing
- Destructive testing
- UI testing
- Session testing

## 📂 Project Structure
**[qa-sauce-demo-project](https://github.com/xoto6bl4/qa-sauce-demo-project)**
- **[README.md](https://github.com/xoto6bl4/qa-sauce-demo-project/blob/main/README.md)**
- **[01-checklists](https://github.com/xoto6bl4/qa-sauce-demo-project/tree/main/01-checklists)**
- **[02-test-design](https://github.com/xoto6bl4/qa-sauce-demo-project/tree/main/02-test-design)**
- **[03-test-cases](https://github.com/xoto6bl4/qa-sauce-demo-project/tree/main/03-test-cases)**
- **[04-test-runs](https://github.com/xoto6bl4/qa-sauce-demo-project/tree/main/04-test-runs)**
- **[05-bug-reports](https://github.com/xoto6bl4/qa-sauce-demo-project/tree/main/05-bug-reports)**

## 🧾 Test Artifacts
- **Test Cases** – detailed scenarios for Login, Products, Cart, and Checkout flows.
- **Test Case Summary CSVs** – structured tables with ID, title, priority, and testing type.
- **Checklists** – quick validation coverage for main application areas.
- **Bug Reports** – defects documented with steps, actual result, expected result, severity, and priority.
- **Test Design Notes** – equivalence classes, negative scenarios, edge cases, user-specific behavior, and destructive testing ideas.
- **Test Data** – Sauce Demo users, valid/invalid credentials, checkout data, and product/cart data.

## 🧰 Tools Used
- GitHub
- Jira (bug reporting practice)
- Postman (basic API testing – optional)
- TestRail
- Chrome browser

## 🌐 Test Environment
- OS: Windows 11
- Browser: Google Chrome (latest version)
- Application URL: https://www.saucedemo.com/

## 📊 Test Execution Results

A manual regression test run was executed in TestRail.

| Status | Count | Percentage |
|---|---:|---:|
| Passed | 128 | 97% |
| Failed | 4 | 3% |
| Blocked | 0 | 0% |
| Skipped | 0 | 0% |
| Untested | 0 | 0% |
| **Total** | **132** | **100%** |

[Test Run Summary](04-test-runs/test-run-summary.md)  
[Test Run Results CSV](04-test-runs/test-run-results.csv)

## 🐞 Defects Found

| Bug ID | Summary | Severity | Priority | Jira Issue |
|---|---|---|---|---|
| BUG-001 | Product buttons remain in `Remove` state after `Reset App State` | Major | Medium | QSD-5 |
| BUG-002 | Cart items remain visible after `Reset App State` on Cart page | Major | Medium | QSD-6 |
| BUG-003 | User can complete checkout with an empty cart | Major | Medium | QSD-7 |
| BUG-004 | User can access order confirmation page directly without completing checkout | Major | Medium | QSD-8 |

[Bug Reports](05-bug-reports/)

## 👤 Kamalov Amal
Manual QA Junior/Trainee  
