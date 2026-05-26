# Products Page Test Cases

Project: QA Sauce Demo Project  
Page: Products Page  
URL: https://www.saucedemo.com/inventory.html

## Test Cases Summary

| ID | Title | Priority | Type |
|---|---|---|---|
| C186 | Verify Products Page Main UI Elements Are Displayed | High | Smoke testing |
| C187 | Verify Product Item Content Is Displayed Correctly | High | Functional testing |
| C189 | Verify Add and Remove Buttons Update Button State and Cart Badge | High | Functional testing |
| C190 | Verify Navigation to Product Details via Product Title | Medium | Functional testing |
| C191 | Verify Navigation to Product Details via Product Image | Medium | Functional testing |
| C192 | Verify Navigation to Shopping Cart from Products Page | High | Smoke testing |
| C193 | Verify Hamburger Menu Can Be Opened and Closed | Medium | Functional testing |
| C194 | Verify Reset App State Clears Cart State | High | Functional testing |
| C195 | Verify Cart Badge Is Hidden When Cart Is Empty | Medium | Functional testing |
| C196 | Verify All Items Menu Item Keeps User on Products Page | Low | Functional testing |
| C197 | Verify About Menu Item Redirects User to Sauce Labs Website | Low | Functional testing |
| C198 | Verify Logout from Products Page Ends User Session | High | Smoke testing |
| C200 | Verify Browser Back Button Does Not Restore Products Page After Logout | High | Security testing |
| C201 | Verify Direct Access to Products Page Without Active Session Is Blocked | High | Security testing |
| C203 | Verify Hamburger Menu Is Visible and Usable on Products Page | Medium | Usability testing |
| C205 | Verify Locked Out User Cannot Access Products Page | High | Security testing |
| C207 | Verify Product Image Issues for Problem User | Medium | Functional testing |
| C208 | Verify Product Data Mapping Issues for Problem User | Medium | Functional testing |
| C209 | Verify Add to Cart Issue for Error User | High | Functional testing |
| C210 | Verify Remove Button Issue for Error User | High | Functional testing |
| C211 | Verify Visual Layout Issues for Visual User | Medium | Usability testing |
| C213 | Verify Products Page Load Time Difference Between Standard and Performance Glitch Users | Low | Performance testing |
| C215 | Verify Sorting by Name A to Z | High | Functional testing |
| C216 | Verify Sorting by Name Z to A | High | Functional testing |
| C217 | Verify Sorting by Price Low to High | High | Functional testing |
| C218 | Verify Sorting by Price High to Low | High | Functional testing |
| C219 | Verify Rapid Sorting Changes Do Not Break Product List State | Medium | Destructive testing |
| C223 | Verify Product Page UI Labels Are Clear and Understandable | Low | Usability testing |
| C224 | Verify Product Information Readability and Contrast | Low | Usability testing |
| C225 | Verify Cart Badge Is Clearly Visible After Adding Product | Medium | Usability testing |
| C228 | Verify Rapid Add and Remove Clicks Do Not Break Cart State | Medium | Destructive testing |
| C231 | Verify Cart State Persists After Products Page Refresh | Medium | Functional testing |
| C232 | Verify Product Button State Persists After Navigation Back to Products Page | Medium | Functional testing |
| C233 | Verify Multiple Products Can Be Added to Cart | High | Functional testing |

---

## Detailed Test Cases

### C186 - Verify Products Page Main UI Elements Are Displayed

**Priority:** High  
**Type:** Smoke testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Observe the header section of the Products page. | The 'Swag Labs' logo is visible, and both the hamburger menu icon (top-left) and the shopping cart icon (top-right) are displayed. |
| 2 | Verify the presence of the page title and the product sorting dropdown. | The 'Products' title is visible below the header, and the active sorting dropdown (defaulting to 'Name (A to Z)') is present. |
| 3 | Inspect the main inventory container. | The inventory list is populated with product items, each containing a product image, name, description, price, and an 'Add to cart' button. |
| 4 | Check the footer section of the page. | The footer is visible and contains social media icons (Twitter, Facebook, LinkedIn) and the copyright text. |

---

### C187 - Verify Product Item Content Is Displayed Correctly

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Inspect the name of every product item displayed in the list. | Each product has a unique, non-empty title displayed as a clickable link. |
| 2 | Inspect the description text provided for every product item. | Each product has a descriptive text block explaining the item features; no descriptions are missing or blank. |
| 3 | Verify the price display for every product item in the list. | Each product displays a price that includes a currency symbol (e.g., '$') followed by a numerical value. |
| 4 | Check the visibility and source of the product images for all items. | Every product displays a unique, relevant image that is correctly rendered without broken links. |

---

### C189 - Verify Add and Remove Buttons Update Button State and Cart Badge

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate any product (e.g., 'Sauce Labs Backpack') and click the 'Add to cart' button. | The button text changes from 'Add to cart' to 'Remove' and the shopping cart badge displays '1'. |
| 2 | Click the 'Add to cart' button for a second product (e.g., 'Sauce Labs Bike Light'). | The button text for the second product changes to 'Remove' and the shopping cart badge updates to '2'. |
| 3 | Click the 'Remove' button for the first product ('Sauce Labs Backpack'). | The button text changes back to 'Add to cart' and the shopping cart badge count decrements to '1'. |
| 4 | Click the 'Remove' button for the second product ('Sauce Labs Bike Light'). | The button text changes back to 'Add to cart' and the shopping cart badge is no longer visible (count reaches 0). |

---

### C190 - Verify Navigation to Product Details via Product Title

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the first product in the list (e.g., 'Sauce Labs Backpack') and click on its name title link. | The browser redirects to the Product Details page for the selected item (e.g., URL contains '/inventory-item.html?id=4'). |
| 2 | Verify that the product name, description, and price on the details page match the item clicked on the Products page. | The product information is consistent with the item selected, confirming the correct page was loaded. |
| 3 | Click the 'Back to products' button. | The user is redirected back to the main Products page (inventory.html). |
| 4 | Repeat the process by clicking on a different product title (e.g., 'Sauce Labs Bolt T-Shirt'). | The browser redirects to the specific Product Details page for the second item selected. |

---

### C191 - Verify Navigation to Product Details via Product Image

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the first product in the inventory list (e.g., Sauce Labs Backpack). | The product image is clearly visible and appears as a clickable element. |
| 2 | Click on the image of the selected product. | The application redirects the user to the Product Details page for that specific item. |
| 3 | Verify the URL and the content of the page. | The URL contains '/inventory-item.html?id=' and the page displays the correct product name, description, and price matching the clicked item. |
| 4 | Click the 'Back to products' button. | The user is redirected back to the main Products page (inventory.html). |

---

### C192 - Verify Navigation to Shopping Cart from Products Page

**Priority:** High  
**Type:** Smoke testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the shopping cart icon in the top right corner of the header. | The shopping cart icon is visible and clickable. |
| 2 | Click on the shopping cart icon. | The user is redirected to the Your Cart page (https://www.saucedemo.com/cart.html). |
| 3 | Verify the page header title. | The page title displays 'Your Cart' and the cart container is visible. |

---

### C193 - Verify Hamburger Menu Can Be Opened and Closed

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the hamburger menu icon (three horizontal lines) in the top-left corner of the Products page and click it. | The side navigation menu slides out from the left and becomes visible, displaying menu items: All Items, About, Logout, and Reset App State. |
| 2 | Locate the 'X' (Close Menu) button within the expanded side navigation menu and click it. | The side navigation menu collapses and is no longer visible on the screen; the user remains on the Products page. |

---

### C194 - Verify Reset App State Clears Cart State

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Click the 'Add to cart' button for at least two different products (e.g., 'Sauce Labs Backpack' and 'Sauce Labs Bike Light'). | The buttons change to 'Remove' and the shopping cart badge displays the number '2'. |
| 2 | Click on the hamburger menu icon (three horizontal lines) in the top left corner of the page. | The sidebar menu opens, displaying options: All Items, About, Logout, and Reset App State. |
| 3 | Click on the 'Reset App State' menu item. | The application state is reset; the shopping cart badge is removed/hidden, and all 'Remove' buttons on the products page revert to 'Add to cart'. |
| 4 | Click the shopping cart icon to navigate to the cart page. | The cart page is displayed and contains no items. |

---

### C195 - Verify Cart Badge Is Hidden When Cart Is Empty

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the shopping cart icon in the top right corner of the header. | The shopping cart icon is visible. |
| 2 | Inspect the shopping cart icon for a numerical badge (counter). | No badge or numerical counter is displayed on or near the shopping cart icon. |
| 3 | Add an item to the cart by clicking 'Add to cart', then click the 'Remove' button for that same item. | The cart badge appears when the item is added and disappears immediately once the item is removed, returning the cart to an empty state with no visible badge. |

---

### C196 - Verify All Items Menu Item Keeps User on Products Page

**Priority:** Low  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the hamburger menu icon (three horizontal lines) in the top-left corner of the page. | The side menu slides open, displaying menu items including 'All Items', 'About', 'Logout', and 'Reset App State'. |
| 2 | Click on the 'All Items' link in the sidebar menu. | The sidebar menu closes, and the user remains on the Products page (inventory.html). The product list remains visible and interactive. |
| 3 | Click on any product name to navigate to its specific product details page. | The browser navigates to the individual product details page. |
| 4 | Open the hamburger menu again and click on the 'All Items' link. | The browser navigates back to the main Products page (https://www.saucedemo.com/inventory.html) and displays the full list of products. |

---

### C197 - Verify About Menu Item Redirects User to Sauce Labs Website

**Priority:** Low  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the hamburger menu icon (three horizontal lines) located at the top-left corner of the header. | The side navigation menu slides open, displaying options including 'All Items', 'About', 'Logout', and 'Reset App State'. |
| 2 | Click on the 'About' link within the menu list. | The browser redirects the user away from the Sauce Demo application to the official Sauce Labs website (https://saucelabs.com/). |
| 3 | Verify the URL and the content of the loaded page. | The URL is 'https://saucelabs.com/' and the page displays the official Sauce Labs corporate homepage content. |

---

### C198 - Verify Logout from Products Page Ends User Session

**Priority:** High  
**Type:** Smoke testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Click on the hamburger menu icon (three horizontal lines) located at the top-left corner of the Products page. | The sidebar menu opens, displaying navigation links including 'All Items', 'About', 'Logout', and 'Reset App State'. |
| 2 | Click on the 'Logout' link within the sidebar menu. | The user is immediately redirected to the Sauce Demo login page (https://www.saucedemo.com/). |
| 3 | Attempt to navigate back to the Products page by clicking the browser's 'Back' button. | The user is not granted access to the Products page; they either remain on the login page or are redirected to it, confirming the session is terminated. |
| 4 | Manually enter the URL 'https://www.saucedemo.com/inventory.html' into the browser address bar and press Enter. | The page does not load the product inventory; the user is redirected to the login page with an error message indicating they must be logged in to view that page. |

---

### C200 - Verify Browser Back Button Does Not Restore Products Page After Logout

**Priority:** High  
**Type:** Security testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened.

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Open the hamburger menu and click 'Logout'. | User is redirected to the Sauce Demo Login page. |
| 2 | Click the browser Back button. | Products page is not restored as an authorized page. |
| 3 | Observe the current page and URL. | User remains unauthenticated and cannot access /inventory.html without logging in again. |

---

### C201 - Verify Direct Access to Products Page Without Active Session Is Blocked

**Priority:** High  
**Type:** Security testing  
**Preconditions:**
- User is not logged in.
- Browser session does not contain an active Sauce Demo session.

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Open the web browser and clear all cookies and session storage for the saucedemo.com domain. | Browser state is clean with no active sessions or stored credentials. |
| 2 | Enter the direct URL 'https://www.saucedemo.com/inventory.html' into the browser address bar and press Enter. | The system prevents access to the inventory page and automatically redirects the user to the Login page (https://www.saucedemo.com/). |
| 3 | Observe the UI for any error messages regarding the unauthorized access attempt. | An error message is displayed on the login page stating: 'Epic sadface: You can only access '/inventory.html' after logging in.' or similar authentication warning. |

---

### C203 - Verify Hamburger Menu Is Visible and Usable on Products Page

**Priority:** Medium  
**Type:** Usability testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Set the browser window resolution to Desktop (e.g., 1920x1080), click the hamburger menu icon (bm-burger-button), and observe the menu items. | The menu expands smoothly; 'All Items', 'About', 'Logout', and 'Reset App State' are clearly visible, properly aligned, and clickable. |
| 2 | Set the browser window resolution to Tablet (e.g., 768x1024), open the hamburger menu, and verify the visibility of all links. | The menu remains fully accessible; all four links are visible within the viewport without overlapping or being cut off. |
| 3 | Set the browser window resolution to Mobile (e.g., 375x667), open the hamburger menu, and verify the visibility of all links. | The menu adapts to the narrow width; all links are stacked correctly, visible, and the touch targets are large enough to be clickable. |
| 4 | While the menu is open in any resolution, click the 'X' (bm-cross-button) to close the menu. | The menu closes successfully, and the main Products page content is fully visible and interactive again. |

---

### C205 - Verify Locked Out User Cannot Access Products Page

**Priority:** High  
**Type:** Security testing  
**Preconditions:**
- Sauce Demo login page is opened: https://www.saucedemo.com/

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Navigate to the Sauce Demo login page (https://www.saucedemo.com/). | The login page loads successfully showing username and password input fields. |
| 2 | Enter 'locked_out_user' in the username field. | The username field is populated with the text 'locked_out_user'. |
| 3 | Enter 'secret_sauce' in the password field. | The password field is populated (characters should be masked). |
| 4 | Click the 'Login' button. | The user remains on the login page. An error message is displayed stating: 'Epic sadface: Sorry, this user has been locked out.'. |
| 5 | Attempt to navigate directly to the Products page by entering 'https://www.saucedemo.com/inventory.html' in the browser address bar. | The user is redirected back to the login page or remains restricted from viewing the inventory. The Products page content is not displayed. |

---

### C207 - Verify Product Image Issues for Problem User

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as problem_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Observe the product images for all items listed on the inventory page (e.g., Sauce Labs Backpack, Sauce Labs Bolt T-Shirt, etc.). | The tester should verify that all product images are replaced with a generic 'broken image' placeholder or a single incorrect image, instead of the specific product photos. |
| 2 | Click on one of the broken images and select 'Inspect' to view the HTML source code. | The 'src' attribute of the tag contains an invalid path or a path that does not match the intended product (e.g., pointing to '/static/media/sl-404.168ba30e.jpg' for all items). |
| 3 | Compare the visual state of the product images against the expected standard product images. | The UI displays a consistent failure across all product cards where unique product imagery is missing, confirming the 'problem_user' profile is active. |

---

### C208 - Verify Product Data Mapping Issues for Problem User

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as problem_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Observe the product images displayed for all items in the inventory list. | All products display the same 'sloth' image instead of unique images corresponding to the product names. |
| 2 | Compare the product names with their respective descriptions and prices. | Product names, descriptions, and prices should appear correctly mapped according to the standard product catalog (e.g., Sauce Labs Backpack should show its specific description and $29.99 price). |
| 3 | Click on the 'Add to Cart' button for a specific product (e.g., Sauce Labs Backpack). | The button may fail to update to 'Remove' or may trigger an action for a different product due to internal mapping errors associated with the problem_user profile. |

---

### C209 - Verify Add to Cart Issue for Error User

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as error_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the 'Sauce Labs Bolt T-Shirt' product on the inventory list. | The product is displayed with an 'Add to cart' button. |
| 2 | Click the 'Add to cart' button for the 'Sauce Labs Bolt T-Shirt'. | The application handles the action according to the error_user profile behavior. The actual button state and cart badge behavior are recorded. |
| 3 | Observe the shopping cart badge icon at the top right of the page. | The cart badge does not increment to '1', indicating a functional failure for this user type. |
| 4 | Attempt to click the 'Add to cart' button for a different product, such as 'Sauce Labs Fleece Jacket'. | Cart content matches the actual cart state shown by the badge and button behavior. |

---

### C210 - Verify Remove Button Issue for Error User

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as error_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate any product on the inventory list (e.g., 'Sauce Labs Backpack') and click the 'Add to cart' button. | The button text changes to 'Remove' and the shopping cart badge displays '1'. |
| 2 | Click the 'Remove' button for the same product. | The button fails to revert to 'Add to cart' or the shopping cart badge fails to disappear/decrease, indicating a functional error specific to the error_user. |
| 3 | Inspect the browser console for any JavaScript errors triggered by the click action. | Console errors are present, confirming that the application logic failed to execute the removal command correctly. |

---

### C211 - Verify Visual Layout Issues for Visual User

**Priority:** Medium  
**Type:** Usability testing  
**Preconditions:**
- User is logged in as visual_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Observe the Products page header, including the logo, burger menu, page title, sorting dropdown, and cart icon. | Header elements are visible and usable. Some visual differences or alignment issues may be present for visual_user. |
| 2 | Observe the product cards in the inventory list. | Product cards are displayed, but some spacing or alignment issues may be visible compared to the standard layout. |
| 3 | Check product images, product names, descriptions, and prices. | Product information is visible, but some elements may have abnormal spacing, shifted positioning, or visual inconsistency. |
| 4 | Check the position of Add to cart buttons for several products. | Some Add to cart buttons may appear misaligned, shifted, or placed inconsistently within product cards. |
| 5 | Observe the shopping cart badge. | The cart badge appears, but it may be visually shifted, incorrectly positioned, or inconsistent with the standard layout. |
| 6 | Open the burger menu. | The side menu opens and remains usable. Some spacing or alignment differences may be visible for visual_user. |
| 7 | Close the burger menu using the X button. | The menu closes, and the user remains on the Products page. |

---

### C213 - Verify Products Page Load Time Difference Between Standard and Performance Glitch Users

**Priority:** Low  
**Type:** Performance testing  
**Preconditions:**
- Browser is opened.
- No active Sauce Demo session is required before starting the test.

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Open the browser and navigate to the Sauce Demo login page. | The login page is displayed successfully. |
| 2 | Log in using 'standard_user' credentials and measure the time taken for the Products page to fully load. | The Products page loads immediately (typically under 1 second) with all product images and elements visible. |
| 3 | Logout from the application via the hamburger menu to return to the login page. | The user is redirected back to the login page and the session is cleared. |
| 4 | Log in using 'performance_glitch_user' credentials and measure the time taken for the Products page to fully load. | There is a significant, noticeable delay (approximately 5 seconds) before the Products page content is rendered. |
| 5 | Compare the loading times recorded for both users. | The 'performance_glitch_user' experiences a consistent performance degradation compared to the 'standard_user', confirming the glitch is profile-specific. |

---

### C215 - Verify Sorting by Name A to Z

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the sorting dropdown menu at the top right of the products list (default is usually 'Name (A to Z)'). | The sorting dropdown is visible and interactable. |
| 2 | If not already selected, click on the sorting dropdown and select the 'Name (A to Z)' option. | The 'Name (A to Z)' option is selected and displayed as the active sorting method. |
| 3 | Observe the order of the product names displayed in the inventory list. | All products are displayed in alphabetical order by name (e.g., 'Sauce Labs Backpack' appears before 'Sauce Labs Bolt T-Shirt'). |
| 4 | Verify the specific placement of the first and last items in the list based on their names. | The first item is 'Sauce Labs Backpack' and the last item is 'Test.allTheThings() T-Shirt (Red)' (or the respective alphabetical first/last items currently in the database). |

---

### C216 - Verify Sorting by Name Z to A

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the sorting dropdown menu (top right of the product list) and click on it. | The dropdown menu expands, displaying four sorting options: 'Name (A to Z)', 'Name (Z to A)', 'Price (low to high)', and 'Price (high to low)'. |
| 2 | Select the 'Name (Z to A)' option from the dropdown list. | The dropdown displays 'Name (Z to A)' as the active selection, and the product list updates immediately. |
| 3 | Inspect the names of the products displayed in the list from top to bottom. | All products are sorted in descending alphabetical order (e.g., 'Test.allTheThings() T-Shirt (Red)' appears before 'Sauce Labs Backpack'). |

---

### C217 - Verify Sorting by Price Low to High

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the sorting dropdown menu at the top right of the products list (defaulted to 'Name (A to Z)'). | The sorting dropdown is visible and interactable. |
| 2 | Click on the dropdown and select the option 'Price (low to high)'. | The dropdown selection updates to 'Price (low to high)' and the product list refreshes immediately. |
| 3 | Inspect the prices of all displayed products from top to bottom. | The products are displayed in ascending order of price (e.g., $7.99, $9.99, $15.99, etc.). |
| 4 | Verify that the first item in the list has the lowest price and the last item has the highest price. | The numerical values of the prices strictly follow a low-to-high sequence across the entire inventory list. |

---

### C218 - Verify Sorting by Price High to Low

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the sorting dropdown menu (top right of the products container) and click on it. | The sorting dropdown menu opens, displaying four options: 'Name (A to Z)', 'Name (Z to A)', 'Price (low to high)', and 'Price (high to low)'. |
| 2 | Select the 'Price (high to low)' option from the dropdown list. | The dropdown selection updates to show 'Price (high to low)' and the product list refreshes immediately. |
| 3 | Inspect the prices of the displayed products from top to bottom. | The products are sorted by price in descending order. The first item should be the most expensive (e.g., Sauce Labs Fleece Jacket at $49.99) and the last item should be the least expensive (e.g., Sauce Labs Onesie at $7.99). |
| 4 | Verify that the numerical values follow a consistent high-to-low sequence across all items in the list. | Every subsequent product price is less than or equal to the price of the product preceding it. |

---

### C219 - Verify Rapid Sorting Changes Do Not Break Product List State

**Priority:** Medium  
**Type:** Destructive testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the sorting dropdown menu (top right of the product list) and click it to expand the options. | The sorting dropdown expands, displaying four options: Name (A to Z), Name (Z to A), Price (low to high), and Price (high to low). |
| 2 | Rapidly select different sorting options in quick succession (e.g., click 'Price (low to high)', then immediately 'Name (Z to A)', then 'Price (high to low)'). | The UI remains responsive without freezing, crashing, or displaying broken image placeholders during the transitions. |
| 3 | Perform a final rapid click on the 'Price (low to high)' option and wait for the page to settle. | The product list stabilizes and correctly displays items sorted by price in ascending order (e.g., Sauce Labs Onesie at $7.99 should be first). |
| 4 | Observe the product images and descriptions during and after the rapid switching. | There is no excessive flickering, and the images correctly match the product descriptions for the final sorted state. |

---

### C223 - Verify Product Page UI Labels Are Clear and Understandable

**Priority:** Low  
**Type:** Usability testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Inspect the labels of the 'Add to cart' buttons for various products. | Buttons are clearly labeled 'Add to cart', indicating their specific action. |
| 2 | Click an 'Add to cart' button and observe the label change. | The button label changes to 'Remove', clearly indicating the action to reverse the previous step. |
| 3 | Examine the sorting dropdown menu and its available options. | The dropdown is labeled with the current sort state (e.g., 'Name (A to Z)'), and options are descriptive: 'Name (A to Z)', 'Name (Z to A)', 'Price (low to high)', and 'Price (high to low)'. |
| 4 | Open the hamburger menu and review the text for each menu item. | Menu items are clearly labeled as 'All Items', 'About', 'Logout', and 'Reset App State', accurately describing their respective destinations or functions. |
| 5 | Verify the product names and the shopping cart icon link. | Product names are displayed as clickable links, and the shopping cart icon is easily identifiable as a navigation element to the cart. |

---

### C224 - Verify Product Information Readability and Contrast

**Priority:** Low  
**Type:** Usability testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Examine the product names, descriptions, and prices displayed on the inventory list. | Text is sharp, font sizes are large enough to read comfortably, and there is a high contrast between the dark text and the white background. |
| 2 | Inspect the 'Add to Cart' and 'Remove' buttons for text clarity and color contrast. | Button labels are clearly legible; the white text on dark/colored backgrounds meets standard visibility expectations. |
| 3 | Open the hamburger menu and verify the readability of the navigation links (All Items, About, Logout, Reset App State). | Menu items are displayed with clear typography and sufficient spacing, making them easy to distinguish and read against the menu background. |
| 4 | Check the shopping cart badge (number icon) for legibility. | The white number is clearly visible and centered within the red badge circle, providing a distinct contrast. |
| 5 | Review the sorting dropdown menu text and the footer area information. | All secondary information, including dropdown options and footer text, remains legible without straining the eyes. |

---

### C225 - Verify Cart Badge Is Clearly Visible After Adding Product

**Priority:** Medium  
**Type:** Usability testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Click the 'Add to cart' button for any product (e.g., Sauce Labs Backpack). | A red circular badge appears over the shopping cart icon containing the number '1'. The badge is high-contrast and clearly legible against the header background. |
| 2 | Add two more different products to the cart. | The badge counter updates immediately to '3'. The text remains centered within the badge and is easy to read. |
| 3 | Scroll down to the bottom of the products list and observe the header/cart icon behavior. | The page scrolls normally. If the header is not fixed, the cart badge may move out of the visible viewport together with the header. This behavior should be documented as actual UI behavior, not treated as a defect unless sticky header behavior is required. |
| 4 | Click the 'Remove' button for one of the added products. | The badge counter immediately updates to '2', maintaining its visual prominence and correct numerical state. |

---

### C228 - Verify Rapid Add and Remove Clicks Do Not Break Cart State

**Priority:** Medium  
**Type:** Destructive testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate any product on the inventory list (e.g., 'Sauce Labs Backpack') and click the 'Add to cart' button. | The button text changes to 'Remove' and the shopping cart badge displays '1'. |
| 2 | Perform multiple rapid, successive clicks (at least 5-10 clicks in quick succession) on the 'Remove' button for that specific product. | The first click successfully removes the item; the button text changes back to 'Add to cart' and the shopping cart badge disappears or decreases by 1. |
| 3 | Observe the application behavior and the state of the button after the rapid clicking sequence is completed. | The application remains stable without freezing or crashing; the button remains in the 'Add to cart' state and does not trigger further state changes or errors. |
| 4 | Click the 'Add to cart' button again for the same product. | The product is successfully added back to the cart, the button changes to 'Remove', and the cart badge displays '1', confirming the functional integrity of the button. |

---

### C231 - Verify Cart State Persists After Products Page Refresh

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Click the 'Add to cart' button for 'Sauce Labs Backpack'. | The button text changes to 'Remove' and the shopping cart badge displays '1'. |
| 2 | Click the 'Add to cart' button for 'Sauce Labs Bike Light'. | The button text changes to 'Remove' and the shopping cart badge updates to '2'. |
| 3 | Refresh the browser page using the browser's reload button or F5 key. | The page reloads successfully and the user remains on the Products page. |
| 4 | Observe the shopping cart badge and the state of the previously selected products. | The shopping cart badge still displays '2', and the buttons for 'Sauce Labs Backpack' and 'Sauce Labs Bike Light' still show 'Remove'. |

---

### C232 - Verify Product Button State Persists After Navigation Back to Products Page

**Priority:** Medium  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the 'Sauce Labs Backpack' and click the 'Add to cart' button. | The button text changes from 'Add to cart' to 'Remove' and the shopping cart badge displays '1'. |
| 2 | Click on the 'Sauce Labs Backpack' name link to navigate to its Product Details page. | The Product Details page for the Sauce Labs Backpack opens, and the button correctly displays 'Remove'. |
| 3 | Click the 'Back to products' button to return to the main inventory page. | The user is redirected back to the Products page. |
| 4 | Verify the state of the 'Sauce Labs Backpack' button on the Products page. | The button for the 'Sauce Labs Backpack' still displays 'Remove' and the cart badge still displays '1'. |
| 5 | Click the 'Remove' button for the 'Sauce Labs Backpack'. | The button text changes back to 'Add to cart' and the shopping cart badge disappears. |
| 6 | Click on the 'Sauce Labs Backpack' image to navigate to the Product Details page again. | The Product Details page opens, and the button correctly displays 'Add to cart'. |
| 7 | Click the 'Back to products' button to return to the main inventory page. | The user is redirected back to the Products page. |
| 8 | Verify the state of the 'Sauce Labs Backpack' button on the Products page. | The button for the 'Sauce Labs Backpack' still displays 'Add to cart' and the cart badge remains empty. |

---

### C233 - Verify Multiple Products Can Be Added to Cart

**Priority:** High  
**Type:** Functional testing  
**Preconditions:**
- User is logged in as standard_user.
- Products page is opened: https://www.saucedemo.com/inventory.html

**Steps:**

| # | Step | Expected Result |
|---:|---|---|
| 1 | Locate the first product in the list (e.g., 'Sauce Labs Backpack') and click the 'Add to cart' button. | The button text changes from 'Add to cart' to 'Remove' and the shopping cart badge displays '1'. |
| 2 | Locate a second different product (e.g., 'Sauce Labs Bike Light') and click the 'Add to cart' button. | The button text for the second product changes to 'Remove' and the shopping cart badge updates to '2'. |
| 3 | Locate a third different product (e.g., 'Sauce Labs Bolt T-Shirt') and click the 'Add to cart' button. | The button text for the third product changes to 'Remove' and the shopping cart badge updates to '3'. |
| 4 | Click on the shopping cart icon at the top right of the page. | The user is navigated to the Cart page, and all three selected items are listed correctly in the cart inventory. |

---

