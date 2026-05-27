# Product Page Checklist – Sauce Demo

## ✅ Positive scenarios

- [ ] Products page opens successfully after login with valid user credentials
- [ ] Page title `Products` is displayed
- [ ] Product list is displayed with all available products
- [ ] Each product displays name, description, price, image, and `Add to cart` button
- [ ] Product details page opens after clicking a product title
- [ ] Product details page opens after clicking a product image
- [ ] `Back to products` button returns user to Products page
- [ ] Shopping cart icon redirects user to Cart page

---

## 🛒 Add / Remove product behavior

- [ ] `Add to cart` button adds selected product to cart
- [ ] Button text changes from `Add to cart` to `Remove` after adding product
- [ ] Cart badge appears after adding one product
- [ ] Cart badge count increases after adding multiple products
- [ ] `Remove` button removes selected product from cart
- [ ] Button text changes from `Remove` back to `Add to cart`
- [ ] Cart badge count decreases after removing product
- [ ] Cart badge disappears when cart becomes empty
- [ ] Multiple different products can be added to cart
- [ ] Product button state persists after navigating to Product Details and back
- [ ] Cart state persists after refreshing the Products page

---

## 🔃 Sorting

- [ ] Sorting dropdown is visible and clickable
- [ ] Products are sorted correctly by `Name (A to Z)`
- [ ] Products are sorted correctly by `Name (Z to A)`
- [ ] Products are sorted correctly by `Price (low to high)`
- [ ] Products are sorted correctly by `Price (high to low)`
- [ ] Product data remains correct after changing sorting options
- [ ] Rapid sorting changes do not break product list state

---

## 🍔 Hamburger menu / Navigation

- [ ] Hamburger menu button is visible on Products page
- [ ] Hamburger menu opens after clicking the menu button
- [ ] Menu displays `All Items`, `About`, `Logout`, and `Reset App State`
- [ ] Hamburger menu closes after clicking the `X` button
- [ ] `All Items` menu option keeps or returns user to Products page
- [ ] `About` menu option redirects user to Sauce Labs website
- [ ] `Logout` menu option logs user out and redirects to Login page
- [ ] `Reset App State` clears cart state
- [ ] `Reset App State` changes all `Remove` buttons back to `Add to cart`

---

## 👤 User-specific behavior

- [ ] `standard_user` can view and use Products page normally
- [ ] `problem_user` product images are checked for incorrect or broken mapping
- [ ] `problem_user` product data mapping is checked against expected product data
- [ ] `error_user` Add to cart behavior is checked for functional issues
- [ ] `error_user` Remove button behavior is checked for functional issues
- [ ] `visual_user` Products page layout is checked for visual issues
- [ ] `performance_glitch_user` Products page loading delay is checked

---

## ❌ Negative / Access scenarios

- [ ] Products page cannot be accessed directly without active login session
- [ ] User is redirected to Login page when accessing Products page without authentication
- [ ] Locked out user cannot access Products page
- [ ] Products page is not restored as an authenticated page after logout using browser Back button
- [ ] Protected Products page access is blocked after manual session/storage clearance

---

## ✨ UI / Usability

- [ ] Main header elements are visible: logo, hamburger menu, cart icon
- [ ] Product names are readable and clearly clickable
- [ ] Product descriptions are readable
- [ ] Product prices are visible and formatted with currency symbol
- [ ] Product images are displayed without broken links for standard user
- [ ] `Add to cart` and `Remove` buttons are visible and understandable
- [ ] Sorting dropdown labels are clear
- [ ] Cart badge is clearly visible after adding products
- [ ] Footer is visible and contains social media links
- [ ] Products page remains usable on common desktop, tablet, and mobile widths

---

## ⚡ Performance checks

- [ ] Products page loads without noticeable delay for `standard_user`
- [ ] Products page loading delay is noticeable for `performance_glitch_user`
- [ ] Product list becomes fully visible after loading delay
- [ ] Page remains stable after performance delay
- [ ] Cart state remains correct after delayed page loading

---

## 💥 Destructive / Edge case checks

- [ ] Rapid Add and Remove clicks do not break cart state
- [ ] Rapid sorting changes do not crash or freeze the page
- [ ] Product list remains consistent after repeated navigation between Product Details and Products page
- [ ] Page refresh does not reset selected product state
- [ ] Cart badge does not show incorrect count after rapid actions
