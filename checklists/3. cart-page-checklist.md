# Cart Page Checklist – Sauce Demo

## ✅ Positive scenarios

- [ ] Cart page opens successfully after clicking the shopping cart icon
- [ ] Cart page URL is `https://www.saucedemo.com/cart.html`
- [ ] Page title `Your Cart` is displayed
- [ ] Cart page displays `QTY` and `Description` columns
- [ ] `Continue Shopping` button is visible and clickable
- [ ] `Checkout` button is visible and clickable
- [ ] `Continue Shopping` button redirects user back to Products page
- [ ] `Checkout` button redirects user to Checkout Step One page
- [ ] Browser Back button returns user to Cart page with cart data preserved after navigation

---

## 🛒 Cart item display

- [ ] One added product is displayed correctly on Cart page
- [ ] Product name, description, price, and quantity are displayed correctly
- [ ] Cart badge count matches the number of items in the cart
- [ ] Multiple selected products are displayed correctly on Cart page
- [ ] All 6 available products can be displayed in Cart after being added
- [ ] Product data in Cart matches product data from Products page
- [ ] Each added product has quantity `1`
- [ ] No duplicate or missing items are displayed in Cart

---

## 🗑️ Remove item behavior

- [ ] Removing one item from a multi-item cart removes only the selected item
- [ ] Cart badge count decreases after removing one item
- [ ] Remaining cart items stay visible with correct data after removing another item
- [ ] Removing the last item clears the cart item list
- [ ] Cart badge disappears when the last item is removed
- [ ] `Continue Shopping` and `Checkout` buttons remain visible when cart becomes empty
- [ ] Rapid double-click on `Remove` button removes item only once
- [ ] Cart remains empty after refresh when the last item was removed

---

## 🧺 Empty cart state

- [ ] Empty Cart page opens successfully
- [ ] Cart item list area is empty when no products are added
- [ ] Shopping cart badge is not visible when cart is empty
- [ ] `Continue Shopping` button remains available in empty cart
- [ ] `Checkout` button remains visible in empty cart
- [ ] Empty cart state does not show broken product rows or incorrect item data

---

## 👤 User-specific behavior

- [ ] `standard_user` can view selected cart items correctly
- [ ] `problem_user` cart item names and prices are checked against selected products
- [ ] `problem_user` product detail link from Cart is checked for correct navigation
- [ ] `error_user` Remove button behavior is checked on Cart page
- [ ] `error_user` item removal does not cause unexpected UI state
- [ ] `visual_user` Cart page layout is checked for visual issues
- [ ] `performance_glitch_user` Cart page loading delay is checked

---

## ❌ Negative / Access scenarios

- [ ] Cart page cannot be accessed directly without active login session
- [ ] User is redirected to Login page when opening Cart URL without authentication
- [ ] User cannot continue using Cart page after session data is cleared
- [ ] User is redirected to Login page after refreshing Cart page with cleared session
- [ ] Cart page cannot be restored as an authenticated page after logout using browser Back button
- [ ] Checkout navigation is blocked if session is cleared before clicking `Checkout`

---

## 🔄 Persistence / Navigation

- [ ] Cart state persists after refreshing Cart page
- [ ] Added products remain in Cart after navigating back to Products page and returning to Cart
- [ ] Cart badge remains consistent after page refresh
- [ ] Browser Back button returns from Products page to Cart page with items preserved
- [ ] Browser Back button returns from Checkout Step One to Cart page with items preserved
- [ ] Cart item data remains consistent after navigation between Cart and Products pages

---

## ✨ UI / Usability

- [ ] Cart page header is visible and readable
- [ ] Cart item list is placed under the page header
- [ ] Product names are readable and clearly displayed
- [ ] Product descriptions are readable
- [ ] Product prices are visible and formatted with currency symbol
- [ ] Quantity column is visible and understandable
- [ ] `Remove` buttons are visible and aligned with their products
- [ ] `Continue Shopping` and `Checkout` buttons are clearly separated
- [ ] Main Cart page elements do not overlap on standard desktop resolution
- [ ] Cart page remains usable on common desktop, tablet, and mobile widths
- [ ] Cart badge is clearly visible when items are present

---

## ⚡ Performance checks

- [ ] Cart page loads without noticeable delay for `standard_user`
- [ ] Cart page loading delay is noticeable for `performance_glitch_user`
- [ ] Cart item list is displayed correctly after loading delay
- [ ] Main Cart page buttons remain usable after delayed loading
- [ ] Navigation from Cart to Products works after performance delay
- [ ] Navigation from Cart to Checkout works after performance delay

---

## 💥 Destructive / Edge case checks

- [ ] Rapid clicks on `Continue Shopping` do not break navigation
- [ ] Rapid clicks on `Checkout` do not break navigation
- [ ] Rapid double-click on `Remove` does not create incorrect cart state
- [ ] Cart page does not crash after repeated refreshes
- [ ] Cart badge does not show incorrect count after rapid remove actions
- [ ] Cart data remains consistent after repeated navigation between Cart, Products, and Checkout pages

---

## 📝 Notes

- Multi-quantity of the same product is not tested because Sauce Demo allows adding each product only once.
- Real payment, shipping, and order history are not part of Cart Page functionality.
