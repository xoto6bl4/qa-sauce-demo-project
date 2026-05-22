# Cart Page Test Design – Sauce Demo

## 🎯 Feature: Cart Page

### Page URL

`https://www.saucedemo.com/cart.html`

### Main Areas Covered

- Cart item list
- Empty cart state
- Product data consistency between Products page and Cart page
- Remove item actions
- Cart badge behavior
- Continue Shopping navigation
- Checkout navigation
- Browser Back / Forward navigation
- Page refresh and cart persistence
- Direct URL access and session restrictions
- User-specific cart behavior
- Basic UI and usability checks
- Performance and destructive scenarios

---

## 🔹 Equivalence Partitioning

### Cart Content State

| Class Type | Test Data / Condition | Expected Result |
|---|---|---|
| Valid class | Cart contains one product | Cart page displays one item with correct name, description, price, quantity, and cart badge count |
| Valid class | Cart contains multiple different products | Cart page displays all selected products with correct details and badge count |
| Valid class | Cart is empty | Cart item list is empty and cart badge is not visible |
| Edge class | Cart contains all available products | All selected products are displayed without missing or duplicated items |
| Defect-prone class | Cart product data does not match Products page data | Issue should be detected and documented |

---

### Remove Item Behavior

| Class Type | Test Data / Condition | Expected Result |
|---|---|---|
| Valid class | Remove one item from a cart with multiple items | Selected item is removed, remaining items stay visible, cart badge decreases |
| Valid class | Remove the last item from the cart | Cart becomes empty and cart badge disappears |
| Valid class | Remove item for `standard_user` | Item is removed correctly |
| Defect-prone class | Remove item for `error_user` | Removal may fail or behave inconsistently and should be documented |
| Edge class | Rapid double-click on Remove button | Item is removed only once and the application remains stable |

---

### Navigation from Cart Page

| Class Type | Test Data / Condition | Expected Result |
|---|---|---|
| Valid class | Click `Continue Shopping` | User is redirected to Products page |
| Valid class | Click `Checkout` with item in cart | User is redirected to Checkout: Your Information page |
| Valid class | Browser Back after Continue Shopping | User returns to Cart page and cart state is preserved |
| Valid class | Browser Back after Checkout navigation | User returns to Cart page and cart state is preserved |
| Edge class | Rapid repeated clicks on Cart navigation buttons | Application remains stable and does not create inconsistent navigation state |

---

## 🔹 State Transition Testing

### Cart State Flow

```text
Empty cart → One item added → Multiple items added → One item removed → Empty cart → Checkout started
```

| State | Action | Expected Result |
|---|---|---|
| Empty cart | Open Cart page | No product rows are displayed and cart badge is hidden |
| Empty cart | Add one product and open Cart page | One product is displayed and cart badge shows `1` |
| One item in cart | Add another product | Cart badge increases and both products are displayed in Cart page |
| Multiple items in cart | Remove one product | Removed item disappears and cart badge decreases |
| One item in cart | Remove last product | Cart becomes empty and cart badge disappears |
| Items in cart | Refresh Cart page | Cart item list and badge state remain consistent |
| Items in cart | Click Checkout | User moves to Checkout Step One |
| User logged out | Try to access Cart page | Access is blocked and user is redirected to Login page |

---

## 🔹 Data Consistency Checks

| Area | Expected Result |
|---|---|
| Product name | Product name on Cart page matches the selected product from Products page |
| Product description | Description matches the corresponding product data |
| Product price | Price matches the value shown on Products page |
| Quantity | Each added product displays quantity `1` |
| Multiple products | All selected products are listed once without duplicates |
| Cart badge | Badge count matches the number of items in the cart |
| Products page ↔ Cart page | Product data remains consistent after navigation between pages |

---

## 🔹 User-Specific Behavior

| User Type | Area Checked | Expected / Observed Behavior |
|---|---|---|
| `standard_user` | Baseline cart behavior | Cart page works normally |
| `problem_user` | Product data and item navigation from Cart page | Incorrect images, data mapping issues, or broken product links may appear and should be documented |
| `performance_glitch_user` | Cart page loading and navigation delay | Noticeable delay may occur, but Cart page and navigation should remain usable |
| `error_user` | Remove item behavior | Remove action may fail or behave inconsistently and should be documented |
| `visual_user` | Cart page visual layout | Visual issues may appear and should be documented |
| `locked_out_user` | Cart page access | User should not access Cart page because login is blocked |

---

## 🔹 Security and Session Checks

| Scenario | Expected Result |
|---|---|
| Direct access to Cart page without active session | User is redirected to Login page |
| Cart page refresh after session storage is cleared | User loses access to Cart page and is redirected to Login page |
| Click Checkout after session is cleared | Application prevents checkout access and redirects user to Login page |
| Browser Back button after logout from Cart flow | Cart page is not restored as an active authenticated session |
| Protected Cart URL access without login | Cart content is not displayed |

---

## 🔹 Usability and UI Checks

| Area | Expected Result |
|---|---|
| Cart page header | `Your Cart` header is visible and correctly placed |
| Cart item list | Product rows are readable and aligned under `QTY` and `Description` columns |
| Product information | Product names, descriptions, prices, and quantities are clear and readable |
| Action buttons | `Continue Shopping`, `Checkout`, and `Remove` buttons are visible, understandable, and clickable |
| Empty cart state | Empty cart is understandable and does not display incorrect product data |
| Cart badge | Badge is visible only when cart contains items and displays correct count |
| Visual layout | Elements do not overlap or break on standard desktop resolution |
| Responsive behavior | Cart page remains usable on desktop, tablet, and mobile-like screen sizes where applicable |

---

## 🔹 Performance Checks

| Scenario | Expected Result |
|---|---|
| Cart page load for `standard_user` | Cart page loads normally |
| Cart page load for `performance_glitch_user` | Noticeable delay may occur, but page eventually loads correctly |
| Continue Shopping navigation for `performance_glitch_user` | Navigation may be delayed but completes successfully |
| Checkout navigation for `performance_glitch_user` | Navigation may be delayed but user eventually reaches Checkout Step One |
| Cart page interaction during delay | Application should remain responsive and not freeze or crash |

---

## 🔹 Destructive / Edge Case Checks

| Scenario | Expected Result |
|---|---|
| Rapid repeated clicks on `Continue Shopping` | Application remains stable and navigates to Products page correctly |
| Rapid repeated clicks on `Checkout` | Application remains stable and navigates to Checkout Step One correctly |
| Rapid double-click on `Remove` | Item is removed only once and no inconsistent cart state appears |
| Page refresh with items in cart | Cart data remains consistent after reload |
| Browser Back / Forward navigation | Cart state remains consistent after navigation between Products, Cart, and Checkout pages |
| Cart page with empty cart | Page remains stable and core navigation buttons remain usable |

---

## 🔹 Test Design Techniques Used

- Equivalence Partitioning
- State Transition Testing
- Data consistency checks
- Negative Testing
- User-specific behavior checks
- Security and session checks
- Usability checks
- Performance checks
- Destructive / edge case testing

---

## 🔹 Notes

Boundary Value Analysis is not applied to the Cart Page because there are no input fields or numeric fields with clearly specified minimum or maximum allowed values.

Cart behavior is mainly tested through state transitions because the page changes depending on whether the cart is empty, contains one item, contains multiple items, or has items removed.

Multi-quantity testing for the same product is not included because Sauce Demo does not provide functionality to add multiple units of the same product. Each selected product appears with quantity `1`.
