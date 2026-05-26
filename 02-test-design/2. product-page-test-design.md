# Product Page Test Design – Sauce Demo

## 🎯 Feature: Product Page / Inventory

### Page URL

`https://www.saucedemo.com/inventory.html`

### Main Areas Covered

- Product list
- Product item content
- Product details navigation
- Add to cart / Remove actions
- Shopping cart badge
- Sorting dropdown
- Hamburger menu
- Reset App State
- Logout / session behavior
- User-specific product page behavior
- Basic UI and usability checks
- Performance and destructive scenarios

---

## 🔹 Equivalence Partitioning

### Product Data Display

| Class Type | Test Data / Condition | Expected Result |
|---|---|---|
| Valid class | Product has name, description, price, image, and Add to cart button | Product item is displayed correctly on the Products page |
| Valid class | Product price contains `$` and numeric value | Price is readable and displayed in correct format |
| Valid class | Product name is clickable | User can open the correct Product Details page |
| Invalid / defect-prone class | Product image is broken, incorrect, or duplicated | Issue should be detected and documented |
| Invalid / defect-prone class | Product name, description, or price does not match expected product data | Issue should be detected and documented |

---

### Add / Remove Product Behavior

| Class Type | Test Data / Condition | Expected Result |
|---|---|---|
| Valid class | Add one product to cart | Button changes to `Remove`, cart badge displays `1` |
| Valid class | Add multiple different products to cart | Cart badge increases according to the number of added products |
| Valid class | Remove one product from cart | Button changes back to `Add to cart`, cart badge decreases |
| Valid class | Remove all selected products | Cart badge disappears when cart becomes empty |
| Edge class | Rapid repeated Add/Remove clicks | Application remains stable and cart state stays consistent |

---

### Sorting Dropdown

| Class Type | Test Data / Condition | Expected Result |
|---|---|---|
| Valid class | Sort by `Name (A to Z)` | Products are sorted alphabetically in ascending order |
| Valid class | Sort by `Name (Z to A)` | Products are sorted alphabetically in descending order |
| Valid class | Sort by `Price (low to high)` | Products are sorted by price from lowest to highest |
| Valid class | Sort by `Price (high to low)` | Products are sorted by price from highest to lowest |
| Edge class | Rapidly switch sorting options | Product list remains stable and displays the final selected sorting order |

---

### Navigation Elements

| Class Type | Test Data / Condition | Expected Result |
|---|---|---|
| Valid class | Click shopping cart icon | User is redirected to Cart page |
| Valid class | Click product name | User is redirected to the correct Product Details page |
| Valid class | Click product image | User is redirected to the correct Product Details page |
| Valid class | Click `Back to products` from Product Details page | User returns to Products page |
| Valid class | Open and close hamburger menu | Menu opens and closes correctly |
| Valid class | Click `All Items` in hamburger menu | User stays on or returns to Products page |
| Valid class | Click `About` in hamburger menu | User is redirected to Sauce Labs website |
| Valid class | Click `Logout` in hamburger menu | User is logged out and redirected to Login page |

---

## 🔹 State Transition Testing

### Cart State from Products Page

```text
Empty cart → Product added → Multiple products added → Product removed → Empty cart
```

| State | Action | Expected Result |
|---|---|---|
| Empty cart | Add one product | Cart badge appears with value `1`, button changes to `Remove` |
| One product in cart | Add another product | Cart badge updates to `2` |
| Multiple products in cart | Remove one product | Cart badge decreases by `1` |
| One product in cart | Remove last product | Cart badge disappears |
| Products selected | Refresh Products page | Cart badge and button states persist |
| Product selected | Navigate to Product Details and back | Button state and cart badge remain consistent |
| Products selected | Use `Reset App State` | Cart badge is removed and all buttons return to `Add to cart` |

---

## 🔹 User-Specific Behavior

| User Type | Area Checked | Expected / Observed Behavior |
|---|---|---|
| `standard_user` | Baseline product page behavior | Products page works normally |
| `problem_user` | Product images and product data mapping | Image or mapping issues may appear and should be documented |
| `performance_glitch_user` | Products page load time | Products page loads with noticeable delay but remains usable |
| `error_user` | Add/Remove actions | Add or Remove actions may fail and should be documented |
| `visual_user` | Product page layout | Visual layout issues may appear and should be documented |
| `locked_out_user` | Product page access | User should not access Products page because login is blocked |

---

## 🔹 Security and Session Checks

| Scenario | Expected Result |
|---|---|
| Direct access to Products page without active session | User is redirected to Login page |
| Browser Back button after logout | Products page is not restored as an authenticated session |
| Logout from Products page | User session ends and protected pages require login again |
| Locked out user attempts to access Products page | Access is blocked |

---

## 🔹 Usability and UI Checks

| Area | Expected Result |
|---|---|
| Main Products page elements | Header, Products title, sorting dropdown, product list, cart icon, and footer are visible |
| Product information | Product names, descriptions, prices, and images are readable and clear |
| Buttons | `Add to cart`, `Remove`, and menu buttons are visible, understandable, and clickable |
| Cart badge | Badge is visible after adding products and clearly shows the correct count |
| Hamburger menu | Menu items are visible, readable, and clickable |
| Visual layout | Page elements do not overlap or break on standard desktop resolution |
| Responsive behavior | Products page remains usable on desktop, tablet, and mobile-like screen sizes where applicable |

---

## 🔹 Performance Checks

| Scenario | Expected Result |
|---|---|
| Products page load for `standard_user` | Page loads normally |
| Products page load for `performance_glitch_user` | Noticeable delay occurs, but the page eventually loads correctly |
| Cart state after delayed loading | Product data, buttons, and cart badge remain correct after the delay |

---

## 🔹 Destructive / Edge Case Checks

| Scenario | Expected Result |
|---|---|
| Rapid Add/Remove clicks | Application does not crash and cart state remains consistent |
| Rapid sorting changes | Product list remains stable and final selected sort order is applied correctly |
| Page refresh after adding products | Cart badge and button states remain consistent |
| Navigation between Product Details and Products page | Product and cart state are preserved |

---

## 🔹 Test Design Techniques Used

- Equivalence Partitioning
- State Transition Testing
- Negative Testing
- User-specific behavior checks
- Security and session checks
- Usability checks
- Performance checks
- Destructive / edge case testing

---

## 🔹 Notes

Product sorting is validated by checking the actual order of product names and prices after selecting each available sorting option.

Cart-related behavior on the Product Page is tested as a state transition because the product button state and cart badge change depending on user actions.
