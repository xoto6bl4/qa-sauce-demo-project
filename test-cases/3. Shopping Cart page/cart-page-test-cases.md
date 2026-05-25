# Cart Page Test Cases

Project: **QA Sauce Demo Project**

Scope: **Cart Page / Shopping Cart functionality**

## Summary

| ID | Title | Priority | Type |
|---|---|---|---|
| C238 | Verify Checkout button redirects standard_user from Cart page to Checkout Step One page | High | Smoke & Sanity |
| C239 | Verify Continue Shopping Navigation for performance_glitch_user | Medium | Performance |
| C240 | Verify Checkout Navigation for performance_glitch_user | Medium | Performance |
| C241 | Verify rapid repeated clicks on Cart navigation buttons do not break page behavior | Medium | Destructive |
| C242 | Verify Browser Back Button Returns User to Cart from Navigation Targets | Medium | Functional |
| C243 | Verify one added product is displayed correctly on Cart page | High | Functional |
| C244 | Verify Empty Cart State Is Displayed Correctly | Medium | Functional |
| C245 | Verify removing one item from a multi-item Cart updates item list and cart badge | High | Functional |
| C246 | Verify Removing Last Item Clears Cart | Medium | Functional |
| C247 | Verify error_user can remove an item from Cart correctly | Medium | Functional |
| C248 | Verify no console errors occur when error_user removes an item from Cart | Medium | Functional |
| C250 | Verify Cart page displays main UI elements correctly | Medium | Usability |
| C254 | Verify Standard Cart Page Layout Alignment | Medium | Usability |
| C255 | Verify Cart page visual layout for visual_user | Medium | Usability |
| C257 | Verify unauthenticated user cannot access Cart page directly | High | Security |
| C258 | Verify standard_user can access Cart page with selected items | High | Functional |
| C260 | Verify user is redirected to Login page after accessing Cart with cleared session | High | Security |
| C261 | Verify Cart State Persists After Page Refresh | High | Functional |
| C263 | Verify Cart page cannot be accessed through browser history after logout | High | Security |
| C264 | Verify Cart page layout and core actions work correctly in supported browsers | Medium | Functional |
| C265 | Verify Cart Item Information Is Readable and Visually Clear | Medium | Usability |
| C266 | Verify Cart page buttons provide visible feedback after click | Low | Usability |
| C267 | Verify Cart page loads selected items correctly for performance_glitch_user | Medium | Performance |
| C268 | Verify Cart page remains responsive during performance_glitch_user loading delay | Medium | Performance |
| C269 | Verify rapid double-click on Remove button removes item only once | Medium | Destructive |
| C270 | Verify Cart page layout remains usable on different screen resolutions | Medium | Usability |
| C272 | Verify product names, descriptions, prices, and quantities are consistent between Products page and Cart page for all products | High | Functional |
| C274 | Verify Cart page displays selected products correctly for problem_user | Medium | Functional |
| C317 | Verify Reset App State clears visible cart items from Cart page | Medium | Functional |

## Detailed Test Cases

### C238 - Verify Checkout button redirects standard_user from Cart page to Checkout Step One page

**Priority:** High

**Type:** Smoke & Sanity

**Preconditions:**

- Log in to Sauce Demo as 'standard_user', add any item to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page is displayed, showing the added item and the 'Checkout' button.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the 'Checkout' button. | The user is redirected to the 'Checkout: Your Information' page. |
| 2 | Verify the current URL and the page header. | The URL is 'https://www.saucedemo.com/checkout-step-one.html ' and the header title displays 'Checkout: Your Information'. |

### C239 - Verify Continue Shopping Navigation for performance_glitch_user

**Priority:** Medium

**Type:** Performance

**Preconditions:**

- Log in to Sauce Demo as 'performance_glitch_user' and navigate directly to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page loads, though a performance delay may be observed during the initial page load.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Locate and click the 'Continue Shopping' button. | The application initiates a redirect; a noticeable delay (approximately 5 seconds) occurs, but the browser does not time out or display error messages. |
| 2 | Observe the final destination URL and page content after the delay. | The user is successfully redirected to the Products page (https://www.saucedemo.com/inventory.html) and the product inventory list is fully visible. |

### C240 - Verify Checkout Navigation for performance_glitch_user

**Priority:** Medium

**Type:** Performance

**Preconditions:**

- Log in to Sauce Demo as 'performance_glitch_user' and add any item to the cart. Expected initial state: User is logged in and the shopping cart badge displays '1'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Cart page by clicking the shopping cart icon. | The Cart page (https://www.saucedemo.com/cart.html) is displayed; a loading delay may be observed during navigation. |
| 2 | Click the 'Checkout' button. | The application initiates the navigation process; a significant delay (approximately 5 seconds) occurs. |
| 3 | Wait for the page to load completely after the delay. | The user is successfully redirected to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html) without any error messages or session timeouts. |

### C241 - Verify rapid repeated clicks on Cart navigation buttons do not break page behavior

**Priority:** Medium

**Type:** Destructive

**Preconditions:**

- Log in to Sauce Demo as 'performance_glitch_user', add any item to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page is displayed, though it may load with a noticeable delay due to the user profile.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Click the 'Continue Shopping' button rapidly multiple times (e.g., 3-5 times) before the page transition begins. | The application initiates the navigation to the Inventory page only once; no console errors or multiple redundant page load requests are triggered. |
| 2 | Navigate back to the Cart page, then click the 'Checkout' button rapidly multiple times before the page transition begins. | The application initiates the navigation to the 'Checkout: Your Information' page (checkout-step-one.html) only once; the UI does not hang or crash due to multiple clicks. |
| 3 | Observe the browser behavior and URL during the transition delay. | The system handles the debouncing correctly, ensuring that only the first click is processed and the user is eventually landed on the correct destination page without duplicate state transitions. |

### C242 - Verify Browser Back Button Returns User to Cart from Navigation Targets

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- Log in as 'standard_user', add 'Sauce Labs Backpack' to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page is displayed, showing the 'Sauce Labs Backpack' in the item list.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Click the 'Continue Shopping' button. | The user is redirected to the Products page (https://www.saucedemo.com/inventory.html). |
| 2 | Click the browser's 'Back' button. | The user is returned to the Cart page; the 'Sauce Labs Backpack' remains visible in the cart list. |
| 3 | Click the 'Checkout' button. | The user is redirected to the Checkout: Your Information page (https://www.saucedemo.com/checkout-step-one.html). |
| 4 | Click the browser's 'Back' button. | The user is returned to the Cart page; the cart state and UI elements (Header, Item List, Buttons) are preserved correctly. |

### C243 - Verify one added product is displayed correctly on Cart page

**Priority:** High

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'standard_user' and ensure the cart is currently empty. Expected initial state: The shopping cart badge is not visible, indicating zero items.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | On the Products page, click the 'Add to cart' button for the 'Sauce Labs Backpack'. | The button text changes to 'Remove' and the shopping cart badge displays the number '1'. |
| 2 | Click on the shopping cart icon to navigate to the Cart page (https://www.saucedemo.com/cart.html). | The Cart page loads successfully with the header 'Your Cart'. |
| 3 | Verify the contents of the cart list area. | Exactly one item is listed in the cart: 'Sauce Labs Backpack' with a quantity of 1 and a price of $29.99. |
| 4 | Observe the shopping cart badge icon while on the Cart page. | The badge continues to display '1', matching the number of items in the list. |

### C244 - Verify Empty Cart State Is Displayed Correctly

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- Navigate to the Sauce Demo login page and log in as 'standard_user'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Ensure no items are added to the cart (if items exist, click 'Remove' for each item) and click on the Shopping Cart icon. | The user is redirected to the Cart page (https://www.saucedemo.com/cart.html). |
| 2 | Observe the cart item list area below the 'QTY' and 'Description' headers. | The cart list area is empty; no product rows or item containers are visible. |
| 3 | Inspect the Shopping Cart icon at the top right of the header. | The shopping cart badge (the red circle with a number) is not visible. |
| 4 | Verify the presence and state of the primary navigation buttons. | The 'Continue Shopping' and 'Checkout' buttons are still visible and functional even when the cart is empty. |

### C245 - Verify removing one item from a multi-item Cart updates item list and cart badge

**Priority:** High

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'standard_user' and add 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' to the cart. Expected initial state: The shopping cart badge displays '2'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Cart page by clicking the shopping cart icon. | The Cart page (https://www.saucedemo.com/cart.html) is displayed showing both items in the list. |
| 2 | Locate the 'Sauce Labs Backpack' item and click its corresponding 'Remove' button. | The 'Sauce Labs Backpack' is immediately removed from the cart item list. |
| 3 | Observe the remaining items in the cart list. | The 'Sauce Labs Bike Light' remains visible in the cart list with its correct details. |
| 4 | Check the shopping cart badge count in the header. | The shopping cart badge count is updated to '1'. |

### C246 - Remove Last Item in Cart

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'standard_user', add exactly one product (e.g., 'Sauce Labs Backpack') to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page is displayed showing one item in the list and the shopping cart badge displays '1'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the 'Remove' button for the single item present in the cart and click it. | The item is immediately removed from the cart item list area. |
| 2 | Observe the shopping cart icon badge at the top right of the page. | The shopping cart badge number is no longer visible. |
| 3 | Verify the state of the cart item list area. | The cart item list area is empty; no product names, descriptions, or prices are displayed. |
| 4 | Verify that the 'Continue Shopping' and 'Checkout' buttons are still visible and functional. | Both buttons remain on the page, allowing the user to navigate away from the empty cart. |

### C247 - Verify error_user can remove an item from Cart correctly

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'error_user' and add 'Sauce Labs Backpack' to the cart. Expected initial state: The product is added and the shopping cart badge displays '1'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Cart page by clicking the shopping cart icon. | The Cart page loads at https://www.saucedemo.com/cart.html and the 'Sauce Labs Backpack' is visible in the item list. |
| 2 | Click the 'Remove' button associated with the 'Sauce Labs Backpack'. | The item should be immediately removed from the cart list and the shopping cart badge should disappear or update to '0'. |
| 3 | Observe the UI for any persistence of the item or lack of response to the click action. | The UI should reflect the removal; for 'error_user', if a defect exists, the item may remain in the list or the 'Remove' button may fail to trigger the deletion. |

### C248 - Verify no console errors occur when error_user removes an item from Cart

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'error_user' and add 'Sauce Labs Backpack' to the cart. Expected initial state: The product is added and the shopping cart badge displays '1'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the Shopping Cart icon to navigate to the Cart page (https://www.saucedemo.com/cart.html). | The Cart page loads, displaying the 'Sauce Labs Backpack' in the item list. |
| 2 | Open the Browser Developer Tools (F12) and navigate to the 'Console' tab. | The console is visible and ready to log activity. |
| 3 | Click the 'Remove' button next to the 'Sauce Labs Backpack'. | The item should be removed from the list and the cart badge should disappear or decrement. |
| 4 | Observe the Browser Console for any red error messages or uncaught exceptions immediately following the click. | No console errors or exceptions should be triggered by the removal action; for 'error_user', document any specific functional failures or logged errors that occur. |

### C250 - Verify Cart page displays main UI elements correctly

**Priority:** Medium

**Type:** Usability

**Preconditions:**

- Log in to Sauce Demo as a 'standard_user' and navigate to the Cart page by clicking the shopping cart icon or visiting https://www.saucedemo.com/cart.html. Expected initial state: The Cart page loads successfully, and the URL is exactly https://www.saucedemo.com/cart.html.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Check the Cart page header. | Header "Your Cart" is visible and correctly positioned at the top of the page. |
| 2 | Check the cart item list area. | Cart item list container is visible and placed under the header. |
| 3 | Check the Continue Shopping button. | Continue Shopping button is visible, readable, clickable, and placed in the lower-left area of the Cart page. |
| 4 | Check the Checkout button. | Checkout button is visible, readable, clickable, and placed in the lower-right area of the Cart page. |
| 5 | Check the general alignment of the header, cart list area, and action buttons. | Main Cart page elements are aligned correctly, do not overlap, and the page looks readable on standard desktop resolution. |

### C254 - Verify Standard Cart Page Layout Alignment

**Priority:** Medium

**Type:** Usability

**Preconditions:**

- Log in to Sauce Demo as 'standard_user' and add at least two items to the cart (e.g., Sauce Labs Backpack and Sauce Labs Bike Light).

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Cart page by clicking the shopping cart icon or visiting https://www.saucedemo.com/cart.html. | The Cart page loads successfully with the URL ending in /cart.html. |
| 2 | Observe the 'Your Cart' header at the top of the main content area. | The header is clearly visible, left-aligned, and does not overlap with the secondary header or the cart list below it. |
| 3 | Inspect the Cart Item List area containing the added products. | The list is positioned below the header; product names, descriptions, and prices are vertically aligned within their respective columns without overlapping adjacent text or borders. |
| 4 | Check the positioning of the 'Continue Shopping' and 'Checkout' buttons at the bottom of the page. | Buttons are positioned below the item list; they are clearly separated from each other and do not overlap with the footer or the last item in the cart list. |
| 5 | Resize the browser window within standard desktop resolutions (e.g., 1280x720 to 1920x1080). | The layout remains responsive; elements maintain their relative spacing and no UI components (header, list, or buttons) collide or become obscured. |

### C255 - Verify Cart page visual layout for visual_user

**Priority:** Medium

**Type:** Usability

**Preconditions:**

- Log in to Sauce Demo as 'visual_user', add 'Sauce Labs Backpack' to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page loads, but visual anomalies may be present compared to the standard layout (e.g., misaligned header or cart icons).

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Inspect the 'Your Cart' header and the cart table headers (QTY, Description) for alignment and spacing. | Headers are visible, but spacing, alignment, or positioning may differ from the standard layout. |
| 2 | Check the displayed cart item: product name, description, price, and quantity. | Product data is visible, but some spacing or alignment issues may be present. |
| 3 | Observe the Remove button for the cart item. | The Remove button is visible and usable, but it may be misaligned or visually inconsistent. |
| 4 | Observe the Continue Shopping and Checkout buttons. | Buttons are visible and clickable, but their placement may be visually incorrect. For visual_user, the Checkout button may appear shifted to the top-right area instead of being aligned with the standard cart page layout. |
| 5 | Check the shopping cart badge icon in the top-right corner. | The cart badge is visible, but it may appear shifted, detached, or visually inconsistent with the standard layout. |
| 6 | Compare the Cart page layout with the same page opened as standard_user. | Visual differences specific to visual_user are documented, such as misplaced buttons, abnormal spacing, shifted badge, or inconsistent alignment. |

### C257 - Verify unauthenticated user cannot access Cart page directly

**Priority:** High

**Type:** Security

**Preconditions:**

- Open a fresh browser session or clear all browser cookies and local storage to ensure no active session exists. Expected initial state: The browser is in a clean state with no active login session for Sauce Demo.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Enter the direct URL for the cart page (https://www.saucedemo.com/cart.html) into the browser address bar and press Enter. | The user is not permitted to view the cart page content. |
| 2 | Observe the resulting page and any error messages displayed. | The user is redirected to the login page (https://www.saucedemo.com/) and an error message is displayed stating 'Epic sadface: You can only access '/cart.html' when you are logged in.' or similar authentication requirement text. |

### C258 - Verify standard_user can access Cart page with selected items

**Priority:** High

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'standard_user' and add all 6 available products to the cart from the inventory page. Expected initial state: The shopping cart badge updates to show '6' items.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the shopping cart icon to navigate to the Cart page (https://www.saucedemo.com/cart.html). | The user is redirected to the Cart page; the header 'Your Cart' is visible, and the URL is correct. |
| 2 | Verify the presence and details of each item in the cart list against the inventory data. | All 6 items are listed. Each item displays the correct Name, Description, and Price (e.g., Sauce Labs Backpack at $29.99, Sauce Labs Onesie at $7.99, etc.). |
| 3 | Check the quantity field for each item in the cart. | The 'QTY' column for each added item displays a value of '1'. |
| 4 | Verify the visibility of the primary action buttons on the Cart page. | The 'Continue Shopping' and 'Checkout' buttons are clearly visible and functional. |

### C260 - Verify user is redirected to Login page after accessing Cart with cleared session

**Priority:** High

**Type:** Security

**Preconditions:**

- Log in to Sauce Demo as 'standard_user', add any item to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page is displayed correctly with the added item visible.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Manually clear the browser cookies and local storage for the site to simulate an expired or cleared session. | Browser storage is cleared; the user remains on the current view until an action is performed. |
| 2 | Refresh the browser page while on the Cart URL. | The user is redirected to the Login page (https://www.saucedemo.com/) and an error message regarding session or access may be displayed. |
| 3 | Log back in, navigate to the Cart page, clear cookies/session again, and click the 'Checkout' button. | The application prevents navigation to the checkout steps and redirects the user back to the Login page. |

### C261 - Verify Cart State Persists After Page Refresh

**Priority:** High

**Type:** Functional

**Preconditions:**

- Log in as 'standard_user', add 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page displays two items: 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' with their respective details.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Refresh the browser page using the browser's refresh button or F5. | The page reloads at the same URL (/cart.html) and both items remain in the cart list with the shopping cart badge still showing '2'. |
| 2 | Click the 'Continue Shopping' button to return to the inventory page. | The user is redirected to the Products page (inventory.html) and the shopping cart badge consistently displays '2'. |
| 3 | Click on the shopping cart icon to return to the Cart page. | The Cart page loads and still contains the 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' with all data (name, price, quantity) intact. |

### C263 - Verify Cart page cannot be accessed through browser history after logout

**Priority:** High

**Type:** Security

**Preconditions:**

- Log in to Sauce Demo as 'standard_user' and add 'Sauce Labs Backpack' to the cart. Expected initial state: User is logged in and the shopping cart badge displays '1'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Cart page by clicking the shopping cart icon. | The URL is 'https://www.saucedemo.com/cart.html ' and the 'Sauce Labs Backpack' is visible in the list. |
| 2 | Open the sidebar menu and click 'Logout'. | The user is redirected to the login page ('https://www.saucedemo.com/'). |
| 3 | Click the browser's 'Back' button to attempt to return to the Cart page. | The application does not display the Cart page with active session data; the user is either redirected back to the login page or the page content is restricted/cleared, requiring a new login. |

### C264 - Verify Cart page layout and core actions work correctly in supported browsers

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- Log in as 'standard_user' and add 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' to the cart, then navigate to the Cart page (https://www.saucedemo.com/cart.html) using a desktop browser (e.g., Chrome, Firefox, or Safari). Expected initial state: The Cart page loads correctly with the header 'Your Cart', the item list displays the two added products, and the 'Continue Shopping' and 'Checkout' buttons are clearly visible and aligned.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Resize the browser window to a tablet resolution (e.g., 768px width) and observe the layout. | The UI elements scale responsively; the cart list, quantity labels, and action buttons remain fully visible and do not overlap or bleed off the screen. |
| 2 | Resize the browser window to a mobile resolution (e.g., 375px width) and observe the layout. | The layout adapts to a mobile view; the 'Your Cart' header remains legible, and the 'Checkout' and 'Continue Shopping' buttons remain easily tappable and correctly stacked or scaled. |
| 3 | Repeat the navigation to the Cart page using a different browser engine (e.g., switch from Chrome/Blink to Firefox/Gecko or Safari/WebKit). | The Cart page renders consistently across different browsers with no broken CSS, missing icons, or font rendering issues. |
| 4 | Click the 'Checkout' button in both desktop and mobile views. | The application successfully navigates to the 'Checkout: Your Information' page (checkout-step-one.html) regardless of the browser or screen size used. |

### C265 - Verify Cart Item Information Is Readable and Visually Clear

**Priority:** Medium

**Type:** Usability

**Preconditions:**

- Log in to Sauce Demo as 'standard_user' and add 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' to the cart. Expected initial state: Products are added successfully and the user is ready to navigate to the cart.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Cart page by clicking the shopping cart icon. | The URL is https://www.saucedemo.com/cart.html and the 'Your Cart' header is displayed. |
| 2 | Inspect the visual presentation of the product names (e.g., 'Sauce Labs Backpack'). | Product names are displayed in a clear, bold font with high contrast (e.g., dark text on a light background) making them easily readable. |
| 3 | Inspect the visual presentation of the product descriptions. | Descriptions are displayed in a legible font size that is distinct from the title, with sufficient line spacing and contrast for easy reading. |
| 4 | Inspect the visual presentation of the product prices (e.g., '$29.99'). | Prices are clearly visible, positioned consistently near the item description, and use a color/font weight that stands out from the descriptive text. |
| 5 | Verify the overall layout clarity of the cart list area. | There is no overlapping text, the background does not interfere with text legibility, and the UI elements (Remove button, Quantity) are clearly separated from the product details. |

### C266 - Verify Cart page buttons provide visible feedback after click

**Priority:** Low

**Type:** Usability

**Preconditions:**

- Log in as 'standard_user', add 'Sauce Labs Backpack' to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The Cart page is displayed with the 'Remove' button for the item and the 'Checkout' button visible.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Hover the mouse cursor over the 'Remove' button and then click it. | The button provides immediate visual feedback upon hovering and clicking, and the item is removed from the list. |
| 2 | Click the 'Checkout' button. | The button provides immediate visual feedback upon the click event before the application navigates to the 'Checkout: Your Information' page. |
| 3 | Hover over and click the 'Cancel' button and then 'Continue Shopping' button. | The button displays a clear visual state change indicating the click was registered before navigating back to the products page. |

### C267 - Verify Cart page loads selected items correctly for performance_glitch_user

**Priority:** Medium

**Type:** Performance

**Preconditions:**

- Log in to Sauce Demo as 'performance_glitch_user' and add 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' to the cart. Expected initial state: Products are added successfully; the shopping cart badge displays '2'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the Shopping Cart icon to navigate to the Cart page (https://www.saucedemo.com/cart.html). | The page begins to load, though a noticeable delay (approximately 5 seconds) may occur before the content is rendered. |
| 2 | Observe the Cart item list area without refreshing the browser or clicking any other buttons. | After the loading delay, the Cart page fully populates with the 'Sauce Labs Backpack' ($29.99) and 'Sauce Labs Bike Light' ($9.99). |
| 3 | Verify the presence of the 'Your Cart' header, 'Continue Shopping' button, and 'Checkout' button once the content appears. | All UI elements are visible and functional; the cart state correctly reflects the items added in the preconditions. |

### C268 - Verify Cart page remains responsive during performance_glitch_user loading delay

**Priority:** Medium

**Type:** Performance

**Preconditions:**

- Log in to Sauce Demo as 'performance_glitch_user', add 'Sauce Labs Backpack' to the cart, and navigate to the Cart page (https://www.saucedemo.com/cart.html). Expected initial state: The page begins to load, but a noticeable delay (approximately 5 seconds) occurs before the cart items are displayed.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | While the cart items are still loading (during the delay), attempt to click on the 'Continue Shopping' button. | The button remains interactive (hover effects or click animations trigger) and the browser successfully initiates navigation back to the inventory page without the UI freezing. |
| 2 | Return to the Cart page and, during the loading delay, attempt to click on the 'Checkout' button. | The button is responsive to user input and the application proceeds to the 'Checkout: Your Information' page once the click is registered. |
| 3 | During the loading delay, attempt to interact with the page header or the shopping cart icon. | The UI does not hang; the browser remains responsive to scrolling and element interaction despite the delayed data retrieval for the product list. |

### C269 - Verify rapid double-click on Remove button removes item only once

**Priority:** Medium

**Type:** Destructive

**Preconditions:**

- Navigate to the Sauce Demo login page and log in as 'standard_user'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Add 'Sauce Labs Backpack' to the cart and click on the Shopping Cart icon. | The Cart page (/cart.html) opens, displaying one item: 'Sauce Labs Backpack'. |
| 2 | Locate the 'Remove' button for the 'Sauce Labs Backpack' and perform a rapid double-click on it. | The item is removed from the cart list immediately after the first click registered. |
| 3 | Observe the Cart item list and the Shopping Cart badge count. | The item list is empty, and the Shopping Cart badge disappears. |
| 4 | Refresh the page and verify the cart state. | The cart remains empty, confirming the removal was processed correctly and only once. |

### C270 - Verify Cart page layout remains usable on different screen resolutions

**Priority:** Medium

**Type:** Usability

**Preconditions:**

- Log in as 'standard_user' and add 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' to the cart. Expected initial state: Products are added successfully and the shopping cart badge displays '2'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Cart page (https://www.saucedemo.com/cart.html) and maximize the browser window to a desktop resolution (e.g., 1920x1080). | The 'Your Cart' header, item list, 'Continue Shopping', and 'Checkout' buttons are aligned correctly with no overlapping elements. |
| 2 | Resize the browser window to a tablet width (e.g., 768px) and inspect the layout. | The product names, descriptions, and prices wrap or scale appropriately; buttons remain fully visible and clickable without overlapping the product text. |
| 3 | Resize the browser window to a mobile width (e.g., 375px) and inspect the layout. | The layout adjusts to the narrow width; the 'Remove' buttons stay aligned with their respective items, and the 'Continue Shopping' and 'Checkout' buttons remain distinct and accessible. |
| 4 | Slowly drag the browser corner to transition between various widths. | The UI components fluidly reposition themselves without breaking the container or causing text to become unreadable or hidden behind buttons. |

### C272 - Verify product names, descriptions, prices, and quantities are consistent between Products page and Cart page for all products

**Priority:** High

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'standard_user', add all 6 available products to the cart from the inventory page, and click on the Shopping Cart icon to navigate to the Cart page. Expected initial state: The user is redirected to 'https://www.saucedemo.com/cart.html ' and the 'Your Cart' header is visible.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Verify the first item: 'Sauce Labs Backpack'. Check that the name is 'Sauce Labs Backpack', the description matches the inventory page, the price is '$29.99', and the quantity is '1'. | Product details for Sauce Labs Backpack are displayed correctly and match the inventory data. |
| 2 | Verify the second item: 'Sauce Labs Bike Light'. Check that the name is 'Sauce Labs Bike Light', the description matches the inventory page, the price is '$9.99', and the quantity is '1'. | Product details for Sauce Labs Bike Light are displayed correctly and match the inventory data. |
| 3 | Verify the third item: 'Sauce Labs Bolt T-Shirt'. Check that the name is 'Sauce Labs Bolt T-Shirt', the description matches the inventory page, the price is '$15.99', and the quantity is '1'. | Product details for Sauce Labs Bolt T-Shirt are displayed correctly and match the inventory data. |
| 4 | Verify the fourth item: 'Sauce Labs Fleece Jacket'. Check that the name is 'Sauce Labs Fleece Jacket', the description matches the inventory page, the price is '$49.99', and the quantity is '1'. | Product details for Sauce Labs Fleece Jacket are displayed correctly and match the inventory data. |
| 5 | Verify the fifth item: 'Sauce Labs Onesie'. Check that the name is 'Sauce Labs Onesie', the description matches the inventory page, the price is '$7.99', and the quantity is '1'. | Product details for Sauce Labs Onesie are displayed correctly and match the inventory data. |
| 6 | Verify the sixth item: 'Test.allTheThings() T-Shirt (Red)'. Check that the name is 'Test.allTheThings() T-Shirt (Red)', the description matches the inventory page, the price is '$15.99', and the quantity is '1'. | Product details for Test.allTheThings() T-Shirt (Red) are displayed correctly and match the inventory data. |
| 7 | Observe the overall list to ensure no duplicate entries or missing items exist. | Exactly 6 unique items are listed in the cart, corresponding to the items added from the Products page. |

### C274 - Verify Cart page displays selected products correctly for problem_user

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- Log in to Sauce Demo as 'problem_user' and add 'Sauce Labs Backpack' ($29.99) and 'Sauce Labs Fleece Jacket' ($49.99) to the cart from the inventory page. Expected initial state: Items are added to the cart; the shopping cart badge displays '2'.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the shopping cart icon to navigate to the Cart page (https://www.saucedemo.com/cart.html). | The Cart page loads. The URL is exactly 'https://www.saucedemo.com/cart.html '. |
| 2 | Compare the names of the items in the cart list with the items added in Step 1. | The item names match 'Sauce Labs Backpack' and 'Sauce Labs Fleece Jacket' exactly. (Note: Problem user may display incorrect images or names; verify if the cart reflects the intended selection). |
| 3 | Verify the prices displayed for both items in the cart. | The prices match the inventory data: Backpack should be $29.99 and Fleece Jacket should be $49.99. |
| 4 | Click on the item name link for 'Sauce Labs Backpack' within the cart. | The user is redirected to the correct item detail page. (Note: Problem user often experiences broken links or 404 errors when clicking product titles). |

### C317 - Verify Reset App State clears visible cart items from Cart page

**Priority:** Medium

**Type:** Functional

**Preconditions:**

- User is logged in as standard_user. At least one product is added to the cart. User is on the Cart page: https://www.saucedemo.com/cart.html.

| Step # | Step | Expected Result |
|---:|---|---|
| 1 | Observe the Cart page and the shopping cart badge. | The added product is displayed in the cart item list, and the cart badge shows the correct number of added items. |
| 2 | Click the burger menu button in the top-left corner. | The side menu opens and displays menu options: All Items, About, Logout, and Reset App State. |
| 3 | Click Reset App State. | The application resets the cart state. |
| 4 | Observe the shopping cart badge. | The cart badge is removed or no longer displays an item count. |
| 5 | Observe the cart item list on the Cart page without refreshing the page. | 	The cart item list becomes empty immediately. No previously added products remain visible. |
