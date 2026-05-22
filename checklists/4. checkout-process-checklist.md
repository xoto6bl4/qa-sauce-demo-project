# Checkout Process Checklist – Sauce Demo

## ✅ Positive scenarios

- [ ] Checkout process starts successfully from Cart page
- [ ] Checkout Step One page opens after clicking `Checkout`
- [ ] Checkout Step One URL is `https://www.saucedemo.com/checkout-step-one.html`
- [ ] Page title `Checkout: Your Information` is displayed
- [ ] User can enter valid First Name, Last Name, and Zip / Postal Code
- [ ] `Continue` button redirects user to Checkout Overview page after valid data
- [ ] Checkout Overview page URL is `https://www.saucedemo.com/checkout-step-two.html`
- [ ] Page title `Checkout: Overview` is displayed
- [ ] `Finish` button completes the order
- [ ] Checkout Complete page URL is `https://www.saucedemo.com/checkout-complete.html`
- [ ] Order confirmation page is displayed after successful checkout
- [ ] `Back Home` button redirects user back to Products page

---

## 📝 Checkout information form

- [ ] First Name field is visible and editable
- [ ] Last Name field is visible and editable
- [ ] Zip / Postal Code field is visible and editable
- [ ] `Continue` button is visible and clickable
- [ ] `Cancel` button is visible and clickable
- [ ] Form submits successfully with valid data
- [ ] Form data is handled correctly with alphanumeric values
- [ ] Form remains stable after entering special characters
- [ ] Form remains stable after entering international characters
- [ ] Form remains stable after entering very long values
- [ ] Checkout flow is not broken by unusual but non-empty input values

---

## ❌ Required field validation

- [ ] Checkout form cannot be submitted with empty First Name
- [ ] Checkout form cannot be submitted with empty Last Name
- [ ] Checkout form cannot be submitted with empty Zip / Postal Code
- [ ] Checkout form cannot be submitted when all fields are empty
- [ ] Correct error message is displayed when First Name is missing
- [ ] Correct error message is displayed when Last Name is missing
- [ ] Correct error message is displayed when Zip / Postal Code is missing
- [ ] Whitespace-only values are checked for required field validation behavior
- [ ] Error message is visible and readable
- [ ] Error message updates after correcting invalid input
- [ ] Error message can be dismissed using the close button if available

---

## 📦 Checkout Overview

- [ ] Checkout Overview displays selected product name correctly
- [ ] Checkout Overview displays selected product quantity correctly
- [ ] Checkout Overview displays selected product price correctly
- [ ] Checkout Overview displays all selected products when multiple products are in cart
- [ ] Item total is displayed
- [ ] Tax value is displayed
- [ ] Total value is displayed
- [ ] Total equals Item total plus Tax
- [ ] Tax and Total values are formatted as currency
- [ ] Product data in Checkout Overview matches Cart page data
- [ ] No duplicate or missing items are displayed in Checkout Overview

---

## 🧭 Navigation / Flow behavior

- [ ] `Cancel` button on Checkout Step One redirects user back to Cart page
- [ ] `Cancel` button on Checkout Overview redirects user back to Products page
- [ ] Browser Refresh on Checkout Overview does not break checkout data
- [ ] Browser Back button behavior during checkout flow is handled without inconsistent data
- [ ] Browser Forward button behavior during checkout flow is handled without inconsistent data
- [ ] Browser Back button after order completion does not cause broken checkout state
- [ ] Direct URL access behavior for checkout pages is checked
- [ ] User cannot access protected checkout pages without active login session
- [ ] Checkout flow remains consistent after navigation between Cart, Checkout Step One, and Checkout Overview

---

## 🎉 Order completion

- [ ] Clicking `Finish` opens Checkout Complete page
- [ ] Confirmation header is displayed on Checkout Complete page
- [ ] Order completion message is displayed
- [ ] Checkout Complete page contains correct final order status
- [ ] `Back Home` button is visible and clickable
- [ ] `Back Home` button returns user to Products page
- [ ] Cart badge is cleared after order completion
- [ ] Cart state is reset after completed purchase
- [ ] User can start a new shopping flow after returning to Products page

---

## 👤 User-specific behavior

- [ ] `standard_user` can complete checkout successfully
- [ ] `problem_user` checkout information form behavior is checked
- [ ] `problem_user` required field input behavior is checked
- [ ] `performance_glitch_user` checkout page loading delay is checked
- [ ] `performance_glitch_user` checkout flow remains usable after delay
- [ ] `error_user` checkout completion behavior is checked
- [ ] `visual_user` checkout pages are checked for visual/layout issues
- [ ] User-specific issues are verified only where they affect checkout flow

---

## 🛡️ Security checks

- [ ] HTML tags entered into checkout fields are treated as plain text or safely handled
- [ ] JavaScript-like input does not execute in checkout fields
- [ ] SQL-like input does not break checkout flow
- [ ] Special characters do not crash the page
- [ ] Protected checkout URLs cannot be accessed without active authentication
- [ ] Direct access to Checkout Complete without completed order is checked for actual behavior
- [ ] Checkout pages do not expose sensitive session or user data in the UI

---

## ✨ UI / Usability

- [ ] Checkout Step One fields are clearly visible
- [ ] Required checkout fields are understandable
- [ ] Error messages are clear and easy to read
- [ ] Error styling is visible to the user
- [ ] Checkout Overview layout is readable
- [ ] Item total, Tax, and Total are easy to distinguish
- [ ] `Cancel`, `Continue`, `Finish`, and `Back Home` buttons have clear labels
- [ ] Checkout flow is easy to follow from Cart to Complete page
- [ ] Checkout pages remain usable on common desktop, tablet, and mobile widths
- [ ] Visual consistency is checked for `visual_user`

---

## ⚡ Performance checks

- [ ] Checkout pages load without noticeable delay for `standard_user`
- [ ] Checkout Step One loading delay is checked for `performance_glitch_user`
- [ ] Checkout Overview loading delay is checked for `performance_glitch_user`
- [ ] Checkout Complete page loads after delay without errors
- [ ] Checkout flow remains functional after delayed page loading
- [ ] No session timeout or broken state appears during performance delay

---

## 💥 Destructive / Edge case checks

- [ ] Very long values in checkout fields do not crash the page
- [ ] Rapid repeated clicks on `Continue` do not break checkout flow
- [ ] Rapid repeated clicks on `Cancel` do not break navigation
- [ ] Rapid repeated clicks on `Finish` do not create inconsistent checkout state
- [ ] Browser refresh during checkout does not break page state
- [ ] Browser Back and Forward navigation during checkout does not break flow
- [ ] Checkout form handles unusual input combinations without layout breaking
- [ ] Checkout pages remain stable after repeated navigation between checkout steps

---

## 📝 Notes

- Boundary Value Analysis is not applied because Checkout fields do not have clear minimum or maximum length requirements.
- Very long input values are treated as destructive / edge case checks, not boundary value tests.
- Real payment, shipping provider selection, order history, and payment method validation are not part of Sauce Demo checkout functionality.
