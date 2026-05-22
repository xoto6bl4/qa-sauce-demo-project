# Checkout Process Test Design – Sauce Demo

## 🎯 Feature: Checkout Process

### Pages in Scope

- Checkout: Your Information (`checkout-step-one.html`)
- Checkout: Overview (`checkout-step-two.html`)
- Checkout: Complete (`checkout-complete.html`)

### Main Elements and Actions

- First Name field
- Last Name field
- Zip / Postal Code field
- Continue button
- Cancel button
- Checkout overview item list
- Item total, tax, and total values
- Finish button
- Back Home button

---

## 🔹 Equivalence Partitioning

### Checkout Information Fields

| Field | Valid Class | Invalid / Edge Classes | Expected Result |
|---|---|---|---|
| First Name | Non-empty text value, e.g. `John` | Empty value, whitespace-only value, special characters, HTML/JS-like input, SQL-like input, very long value, international characters | Valid non-empty input allows proceeding. Invalid or unusual input should be handled without crash, layout break, or script execution. |
| Last Name | Non-empty text value, e.g. `Doe` | Empty value, whitespace-only value, special characters, HTML/JS-like input, SQL-like input, very long value, international characters | Valid non-empty input allows proceeding. Invalid or unusual input should be handled safely. |
| Zip / Postal Code | Non-empty value, e.g. `12345` | Empty value, whitespace-only value, different non-empty formats, special characters, SQL-like input, very long value | Empty value blocks checkout. Other non-empty values should be handled according to actual application behavior without breaking the flow. |

---

## 🔹 Required Field Validation

| Scenario | Expected Result |
|---|---|
| First Name is empty, other fields are valid | User remains on Checkout: Your Information page and required field error is displayed. |
| Last Name is empty, other fields are valid | User remains on Checkout: Your Information page and required field error is displayed. |
| Zip / Postal Code is empty, other fields are valid | User remains on Checkout: Your Information page and required field error is displayed. |
| All fields are empty | User remains on Checkout: Your Information page and the first required field error is displayed. |
| Fields contain only spaces | Application should handle the input safely and validation behavior should be verified according to actual system behavior. |

---

## 🔹 Checkout Flow Testing

### Main Flow

```text
Cart page → Checkout: Your Information → Checkout: Overview → Checkout: Complete → Products page
```

| Flow Stage | Test Focus | Expected Result |
|---|---|---|
| Start checkout from Cart page | User opens checkout with items in cart | Checkout: Your Information page is displayed. |
| Submit valid information | User enters valid First Name, Last Name, and Zip Code | User is redirected to Checkout: Overview. |
| Review order | User verifies product data and totals | Item data, item total, tax, and total are displayed consistently. |
| Finish order | User clicks Finish | User is redirected to Checkout: Complete. |
| Return home | User clicks Back Home | User is redirected to Products page. |

---

## 🔹 State Transition Testing

### Checkout State Flow

```text
Cart with item(s)
→ Checkout information form
→ Validation error OR Checkout overview
→ Order complete
→ Cart state reset
```

| State | Action | Expected Result |
|---|---|---|
| Cart contains item(s) | Click Checkout | Checkout information page opens. |
| Checkout information page | Submit empty required field | User stays on the same page and sees validation error. |
| Checkout information page | Submit valid data | Checkout overview page opens. |
| Checkout overview page | Click Cancel | User returns to Products page. |
| Checkout overview page | Click Finish | Checkout complete page opens. |
| Checkout complete page | Click Back Home | User returns to Products page and cart badge is reset. |

---

## 🔹 Data Consistency Checks

| Area | Test Focus | Expected Result |
|---|---|---|
| Single item checkout | Product name, quantity, and price on Checkout Overview | Data matches the item added to the cart. |
| Multiple item checkout | All selected products on Checkout Overview | All selected products are displayed with correct names, quantities, and prices. |
| Item total | Sum of all item prices | Item total matches the sum of products in the order. |
| Tax | Tax value based on application logic | Tax is displayed and calculated consistently based on item total. |
| Grand total | Item total + tax | Total value matches item total plus tax. |

> Note: Tax validation is treated as a consistency check based on the value displayed by the application. It is not based on external business requirements because no official tax rule is provided.

---

## 🔹 Navigation Checks

| Scenario | Expected Result |
|---|---|
| Cancel from Checkout: Your Information page | User returns to Your Cart page. |
| Cancel from Checkout: Overview page | User returns to Products page. |
| Browser refresh on Checkout: Overview page | Page reloads without losing visible order data. |
| Browser Back/Forward during checkout | Application handles navigation without crash or inconsistent checkout state. |
| Browser Back after order completion | Application should not crash or create inconsistent visible order/cart state. |
| Direct URL access to Checkout Complete without completed order | Actual application behavior is verified without assuming that access must be blocked. |

---

## 🔹 User-Specific Behavior Checks

| User | Test Focus | Expected Result |
|---|---|---|
| `standard_user` | Baseline checkout flow | User can complete checkout successfully from cart to confirmation page. |
| `problem_user` | Checkout information form behavior | User-specific field/input issue is verified where it affects checkout progression. |
| `performance_glitch_user` | Page loading and transition delay | Checkout pages may load with noticeable delay but should remain usable. |
| `error_user` | Checkout completion behavior | Actual behavior is verified when attempting to complete checkout. |
| `visual_user` | Checkout UI consistency | Layout and visual presentation are compared against standard user behavior. |

---

## 🔹 Security Checks

| Scenario | Expected Result |
|---|---|
| HTML input in checkout fields | HTML is not executed or rendered in a harmful way. |
| JavaScript-like input in checkout fields | Script is not executed; no alert or unexpected behavior occurs. |
| SQL-like input in checkout fields | Input is treated as plain text and does not break checkout logic. |
| Direct checkout URL access without valid flow/session | Access behavior is verified and protected-page behavior should remain safe. |

---

## 🔹 Destructive / Edge Case Checks

| Scenario | Expected Result |
|---|---|
| Very long values in checkout fields | Application remains stable; layout does not break and page does not crash. |
| Rapid repeated clicks on Continue | Checkout flow does not break or create inconsistent page state. |
| Browser refresh during checkout | Application handles refresh without crash or broken UI state. |
| Browser Back/Forward during checkout | Navigation does not cause crash or inconsistent visible data. |
| Empty cart reaches checkout by direct URL | Actual behavior is verified as an edge case; application should not crash. |

---

## 🔹 Usability Checks

| Area | Expected Result |
|---|---|
| Error messages | Error messages are visible, readable, and clearly explain missing required fields. |
| Required fields | The form clearly shows what information is needed to continue checkout. |
| Button labels | Continue, Cancel, Finish, and Back Home labels are clear and understandable. |
| Checkout overview | Product data and payment summary are easy to read. |
| Checkout complete page | Confirmation message clearly communicates successful order completion. |
| Visual user layout | UI anomalies are checked where they affect checkout readability or usability. |

---

## 🔹 Techniques Applied

- Equivalence Partitioning
- Negative Testing
- State Transition Testing
- Data Consistency Checks
- Security Checks
- Destructive / Edge Case Testing
- User-Specific Behavior Checks
- Basic UI and Usability Checks
- Performance-Oriented Checks

---

## 🔹 Notes

Boundary Value Analysis is not applied to the checkout input fields because the application does not provide clear minimum or maximum length requirements for First Name, Last Name, or Zip / Postal Code.

Very long values are treated as destructive or edge case checks, not as boundary value tests.

Multi-quantity testing for the same product is not applied because Sauce Demo does not allow adding multiple units of the same product. Each product can only be added once.
