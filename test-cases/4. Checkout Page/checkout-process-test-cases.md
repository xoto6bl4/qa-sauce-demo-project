# Sauce Demo Checkout Process Test Cases

Project: QA Sauce Demo Project
Section: Checkout Process
URLs:
- https://www.saucedemo.com/checkout-step-one.html
- https://www.saucedemo.com/checkout-step-two.html
- https://www.saucedemo.com/checkout-complete.html

## Test Cases Summary

| ID | Title | Priority | Type |
|---|---|---|---|
| C276 | Single Item Data Accuracy | Medium | Functional testing |
| C277 | Multiple Items Data Accuracy | Medium | Functional testing |
| C278 | Item Total Calculation Logic | High | Functional testing |
| C279 | Verify Tax Is Calculated Consistently Based on Item Total | High | Functional testing |
| C280 | Grand Total Calculation Logic | High | Functional testing |
| C281 | Finish Button Navigation | High | Functional testing |
| C282 | Cancel Button Navigation from Checkout Overview | Medium | Functional testing |
| C283 | Page Refresh Persistence | Medium | Functional testing |
| C284 | Browser History Navigation Persistence | Medium | Functional testing |
| C285 | Successful Form Submission with Valid Data | High | Functional testing |
| C286 | Mandatory Field Validation - Missing First Name | High | Functional testing |
| C287 | Mandatory Field Validation - Missing Last Name | High | Functional testing |
| C288 | Mandatory Field Validation - Missing Zip Code | High | Functional testing |
| C289 | Mandatory Field Validation - All Fields Empty | High | Functional testing |
| C290 | Whitespace-Only Input Handling | Medium | Functional testing |
| C291 | Extreme String Length Handling | Medium | Destructive testing |
| C292 | Special Character Handling | Medium | Functional testing |
| C293 | Script and HTML Injection Prevention | High | Security testing |
| C294 | SQL Injection Pattern Handling | High | Security testing |
| C297 | Back Home Navigation Redirect | Medium | Functional testing |
| C298 | Cart State Reset After Completion | High | Functional testing |
| C299 | Browser Back Navigation After Order Completion | Medium | Destructive testing |
| C300 | Direct URL Access to Checkout Complete Without Completed Order | Medium | Security testing |
| C301 | Standard User Baseline Checkout Success | High | Smoke testing |
| C302 | Checkout Page Loading Behavior for Performance Glitch User | Medium | Performance testing |
| C303 | Performance Glitch - Overview Page Transition Delay | Medium | Performance testing |
| C304 | Problem User - Field Input Restriction | High | Functional testing |
| C305 | Checkout Completion Behavior for Error User | High | Functional testing |
| C306 | Checkout Pages Visual Consistency for Visual User | Medium | Usability testing |
| C308 | Verify checkout cannot be completed with an empty cart | Medium | Functional testing |
| C310 | Cancel Button Navigation from Checkout Information Page | Medium | Functional testing |
| C311 | Error Message UI Visibility and Updates | Medium | Usability testing |
| C313 | Verify checkout form behavior with international characters in name fields | Low | Functional testing |
| C314 | Zip Code Field Handling with Different Non-Empty Values | Low | Functional testing |
| C316 | Repeated Continue Button Click Handling | Medium | Destructive testing |

---

## Detailed Test Cases

## C276 — Single Item Data Accuracy

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to Sauce Demo as 'standard_user' and add one item (e.g., 'Sauce Labs Backpack') to the cart. | The item is successfully added to the cart. |
| Navigate to the Cart page and click the 'Checkout' button. | The user is redirected to the 'Checkout: Your Information' page. |
| Enter valid information (First Name: Harry, Last Name: Potter, Zip Code: 12345) and click 'Continue'. | The user is redirected to the 'Checkout: Overview' page (checkout-step-two.html). |
| Verify the item name displayed in the item list. | The item name matches the product added (e.g., 'Sauce Labs Backpack'). |
| Verify the quantity displayed for the item. | The quantity is displayed as '1'. |
| Verify the individual item price displayed in the list. | The price matches the product's original price (e.g., '$29.99'). |

## C277 — Multiple Items Data Accuracy

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to Sauce Demo as 'standard_user' and add at least three different items (e.g., Sauce Labs Backpack, Sauce Labs Bike Light, and Sauce Labs Bolt T-Shirt) to the cart. | Items are successfully added to the shopping cart. |
| Navigate to the Cart page and click the 'Checkout' button. | The 'Checkout: Your Information' page is displayed. |
| Enter valid information (First Name: Harry, Last Name: Potter, Zip Code: 12345) and click the 'Continue' button. | The user is redirected to the 'Checkout: Overview' page. |
| Review the list of items displayed in the 'QTY' and 'Description' columns. | All selected items are listed. Each item displays the correct quantity (1) and the correct individual price matching the product catalog. |
| Verify the 'Item total' value at the bottom of the list. | The 'Item total' correctly displays the sum of the individual prices of all items in the list (e.g., $29.99 + $9.99 + $15.99 = $55.97). |

## C278 — Item Total Calculation Logic

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to Sauce Demo as 'standard_user' and add 'Sauce Labs Backpack' ($29.99) and 'Sauce Labs Bike Light' ($9.99) to the cart. | Items are successfully added to the cart. |
| Navigate to the Cart page and click the 'Checkout' button. | The 'Checkout: Your Information' page is displayed. |
| Enter 'Harry' in the First Name field, 'Potter' in the Last Name field, '12345' in the Zip/Postal Code field, and click 'Continue'. | The 'Checkout: Overview' page is displayed. |
| Locate the 'Item total' label under the payment and shipping information. | The 'Item total' displays 'Item total: $39.98', which is the correct sum of the individual item prices ($29.99 + $9.99). |
| Verify the 'Total' field at the bottom of the summary. | The 'Total' displays the sum of the 'Item total' ($39.98) and the 'Tax' amount displayed on the page. |

## C279 — Verify Tax Is Calculated Consistently Based on Item Total

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to Sauce Demo as 'standard_user', add 'Sauce Labs Backpack' ($29.99) and 'Sauce Labs Bike Light' ($9.99) to the cart, and navigate to the 'Checkout: Your Information' page. | The user is on the 'Checkout: Your Information' page. |
| Enter 'Harry' in First Name, 'Potter' in Last Name, and '12345' in Zip/Postal Code, then click the 'Continue' button. | The user is redirected to the 'Checkout: Overview' page. |
| Locate the 'Item total' value and the 'Tax' value displayed in the price summary section. | The 'Item total' displays 'Item total: $39.98' (the sum of $29.99 and $9.99). |
| Calculate the tax manually using the system's 8% tax rate ($39.98 * 0.08 = $3.1984, rounded to $3.20) and compare it with the displayed 'Tax' value. | The 'Tax' value is displayed as '$3.20', matching the 8% calculation rounded to two decimal places. |
| Verify the 'Total' value displayed at the bottom of the summary. | The 'Total' displays '$43.18', which is the exact sum of the 'Item total' ($39.98) and the 'Tax' ($3.20). |

## C280 — Grand Total Calculation Logic

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to Sauce Demo as 'standard_user', add multiple items to the cart, and navigate to the 'Checkout: Your Information' page. | The user is on the 'Checkout: Your Information' page. |
| Enter valid information (First Name: Harry, Last Name: Potter, Zip Code: 12345) and click the 'Continue' button. | The user is redirected to the 'Checkout: Overview' page. |
| Locate the 'Item total' value (sum of individual item prices) and the 'Tax' value displayed in the summary info. | Both values are clearly visible and formatted as currency (e.g., Item total: $XX.XX, Tax: $X.XX). |
| Manually calculate the sum of item total and Tax. | The calculated sum is obtained and can be compared with the displayed Total value. |
| Compare the calculated sum with the value displayed next to the 'Total' label at the bottom of the summary. | The 'Total' value displayed on the page exactly matches the sum of the 'Item total' and 'Tax'. |

## C281 — Finish Button Navigation

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to Sauce Demo as a 'standard_user'
- Add any item to the cart
- Proceed through the 'Checkout: Your Information' page by entering valid details (First Name: Harry, Last Name: Potter, Zip Code: 12345).

| Step | Expected Result |
|---|---|
| Review the order details and click the 'Finish' button at the bottom of the page. | The user is redirected to the 'Checkout: Complete!' page (checkout-complete.html). |
| Verify the presence of the order completion header and the confirmation message. | The page displays the header 'Thank you for your order!' and the text 'Your order has been dispatched, and will arrive just as fast as the pony can get there!'. |
| Verify that the 'Back Home' button is visible on the completion page. | The 'Back Home' button is present, confirming the final step of the checkout flow is reached. |

## C282 — Cancel Button Navigation from Checkout Overview

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to the Sauce Demo website as a 'standard_user'. | The user is successfully logged in and redirected to the Products page. |
| Add any item to the cart and click on the 'Shopping Cart' icon. | The user is redirected to the Cart page, and the selected item is visible. |
| Click the 'Checkout' button. | The user is redirected to the 'Checkout: Your Information' page (checkout-step-one.html). |
| Click the 'Cancel' button located next to the 'Continue' button. | The checkout process is aborted, and the user is redirected back to the 'Your Cart' page (cart.html). |
| Proceed to the 'Checkout: Your Information' page again, fill in valid details (First Name: Harry, Last Name: Potter, Zip Code: 12345), and click 'Continue'. | The user is redirected to the 'Checkout: Overview' page (checkout-step-two.html). |
| Click the 'Cancel' button located at the bottom of the overview list. | The checkout process is aborted, and the user is redirected back to the main 'Products' page (inventory.html). |

## C283 — Page Refresh Persistence

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to Sauce Demo as 'standard_user', add at least two items to the cart, and navigate to the 'Checkout: Your Information' page. | The 'Checkout: Your Information' page is displayed. |
| Enter valid details (First Name: Harry, Last Name: Potter, Zip Code: 12345) and click the 'Continue' button. | The user is redirected to the 'Checkout: Overview' page (checkout-step-two.html). |
| Observe and note the listed items, Item total, Tax, and Total price. | The product names, quantities, and prices are displayed correctly with the calculated total. |
| Perform a browser refresh (F5 or Refresh button). | The page reloads and the user remains on the 'Checkout: Overview' page. |
| Verify the displayed order information and price calculations after the refresh. | All previously noted items, quantities, Item total, Tax, and Total price remain visible and unchanged. |
| Click the 'Finish' button. | The order is successfully completed, and the user is redirected to the 'Checkout: Complete!' page. |

## C284 — Browser History Navigation Persistence

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- —

| Step | Expected Result |
|---|---|
| Log in to Sauce Demo as 'standard_user', add any item to the cart, and proceed to the 'Checkout: Your Information' page. | The 'Checkout: Your Information' page (checkout-step-one.html) is displayed. |
| Enter 'Harry' for First Name, 'Potter' for Last Name, and '12345' for Zip/Postal Code, then click the 'Continue' button. | The user is redirected to the 'Checkout: Overview' page (checkout-step-two.html) showing the item details and price total. |
| Click the browser's 'Back' button. | The browser returns to the 'Checkout: Your Information' page. The application should handle the navigation without errors, broken layout, or inconsistent checkout state. The form fields may be cleared if the application does not persist checkout information. |
| Click the browser's 'Forward' button. | The browser returns to the 'Checkout: Overview' page; the correct item details, payment information, and total price are still displayed. |
| Click the 'Finish' button. | The order is successfully processed, and the user is redirected to the 'Checkout: Complete' page (checkout-complete.html). |

## C285 — Successful Form Submission with Valid Data

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' into the 'First Name' input field. | The 'First Name' field is populated with the text 'Harry'. |
| Enter 'Potter' into the 'Last Name' input field. | The 'Last Name' field is populated with the text 'Potter'. |
| Enter '1488' into the 'Zip/Postal Code' input field. | The 'Zip/Postal Code' field is populated with the text '1488'. |
| Click the 'Continue' button. | The user is successfully redirected to the 'Checkout: Overview' page (https://www.saucedemo.com/checkout-step-two.html). |
| Verify the page header and content on the redirected page. | The page title displays 'Checkout: Overview' and the item(s) added to the cart are listed with the correct price and quantity. |

## C286 — Mandatory Field Validation - Missing First Name

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Leave the 'First Name' field empty. | The 'First Name' input field remains blank. |
| Enter 'Potter' into the 'Last Name' field and '12345' into the 'Zip/Postal Code' field. | The fields are populated with the provided values. |
| Click the 'Continue' button. | The form is not submitted, and the user remains on the 'Checkout: Your Information' page. |
| Observe the error message displayed on the page. | An error message appears stating: 'Error: First Name is required'. |

## C287 — Mandatory Field Validation - Missing Last Name

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' into the 'First Name' field. | The 'First Name' field is populated with the text 'Harry'. |
| Leave the 'Last Name' field empty. | The 'Last Name' field remains blank. |
| Enter '12345' into the 'Zip/Postal Code' field. | The 'Zip/Postal Code' field is populated with the text '12345'. |
| Click the 'Continue' button. | The form is not submitted, the user remains on the 'Checkout: Your Information' page, and an error message is displayed stating: 'Error: Last Name is required'. |

## C288 — Mandatory Field Validation - Missing Zip Code

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' in the First Name field. | The First Name field is populated with 'Harry'. |
| Enter 'Potter' in the Last Name field. | The Last Name field is populated with 'Potter'. |
| Leave the Zip/Postal Code field empty and click the 'Continue' button. | The form is not submitted, the user remains on the 'Checkout: Your Information' page, and an error message is displayed stating: 'Error: Postal Code is required'. |

## C289 — Mandatory Field Validation - All Fields Empty

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Leave the 'First Name', 'Last Name', and 'Zip/Postal Code' fields completely empty. | The input fields remain empty without any default text. |
| Click the 'Continue' button. | The system prevents progression to the next step and displays an error message: 'Error: First Name is required'. |
| Observe the visual state of the input fields and the error container. | The error message is clearly visible at the bottom of the form, and the input fields may be highlighted with error icons (X) to indicate validation failure. |

## C290 — Whitespace-Only Input Handling

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter multiple spaces into the 'First Name' field and valid data into 'Last Name' (Potter) and 'Zip/Postal Code' (12345). Click the 'Continue' button. | The application accepts the input |
| Clear the fields. Enter valid data into 'First Name' (Harry), multiple spaces into the 'Last Name' field, and valid data into 'Zip/Postal Code' (12345). Click the 'Continue' button. | The application accepts the input |
| Clear the fields. Enter valid data into 'First Name' (Harry), 'Last Name' (Potter), and multiple spaces into the 'Zip/Postal Code' field. Click the 'Continue' button. | The application accepts the input |
| Clear all fields and enter only spaces/tabs into all three input fields. Click the 'Continue' button. | The application accepts the input and redirects the user to the 'Checkout: Overview' page (checkout-step-two.html) without any errors or crashes. |

## C291 — Extreme String Length Handling

**Priority:** Medium
**Type:** Destructive testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| In the 'First Name' field, enter a string of 1000+ characters (e.g., a long sequence of 'A's). | The field accepts the input without the browser freezing or the application crashing. |
| In the 'Last Name' field, enter a string of 1000+ characters. | The field accepts the input; the UI layout remains intact without horizontal scrolling or element overlapping. |
| In the 'Zip/Postal Code' field, enter a string of 1000+ characters. | The field accepts the input; no immediate validation error is triggered by the length alone. |
| Click the 'Continue' button. | The application processes the request and redirects the user to the 'Checkout: Overview' page. |
| Click the 'Finish' button. | The order is successfully completed, and the user is redirected to the 'Checkout: Complete!' page showing the 'Thank you for your order!' message. |

## C292 — Special Character Handling

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter '!@#$%' in the First Name field. | The characters '!@#$%' are displayed in the First Name field as literal text. |
| Enter '^&*()' in the Last Name field. | The characters '^&*()' are displayed in the Last Name field as literal text. |
| Enter '12-34!@' in the Zip/Postal Code field. | The characters '12-34!@' are displayed in the Zip/Postal Code field as literal text. |
| Click the 'Continue' button. | The application accepts the input and redirects the user to the 'Checkout: Overview' page (checkout-step-two.html) without any errors or crashes. |
| Review the 'Checkout: Overview' page. | The page loads correctly, displaying the product information and price totals; the application remains stable despite the special character inputs from the previous step. |

## C293 — Script and HTML Injection Prevention

**Priority:** High
**Type:** Security testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| In the 'First Name' field, enter: alert('XSS') | The script string is accepted as input without triggering any browser alert or script execution. |
| In the 'Last Name' field, enter: BoldTest | The HTML string is accepted as input. |
| In the 'Zip/Postal Code' field, enter: 12345 and click the 'Continue' button. | The user is redirected to the 'Checkout: Overview' page. |
| Observe the 'Shipping Information' or any area where the user's name might be reflected on the 'Checkout: Overview' page. | The input strings are rendered literally as plain text. No text appears in bold, and no JavaScript alerts are triggered. |
| Click the 'Finish' button and observe the 'Checkout: Complete' page. | The order is completed successfully, and the application remains stable without executing the injected payloads. |

## C294 — SQL Injection Pattern Handling

**Priority:** High
**Type:** Security testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter "' OR 1=1 --" into the First Name field. | The input is accepted and displayed as a literal string in the field. |
| Enter "'; DROP TABLE users; --" into the Last Name field. | The input is accepted and displayed as a literal string in the field. |
| Enter "12345" into the Zip/Postal Code field and click the 'Continue' button. | The application does not crash or display database errors; the user is successfully redirected to the 'Checkout: Overview' page. |
| Review the 'Checkout: Overview' page and click the 'Finish' button. | The order is processed normally, and the user is redirected to the 'Checkout: Complete' page. |

## C297 — Back Home Navigation Redirect

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'

| Step | Expected Result |
|---|---|
| Add any item to the cart and proceed through the checkout process (Cart -> Checkout: Your Information -> Checkout: Overview). | User reaches the 'Checkout: Overview' page. |
| Click the 'Finish' button. | The 'Checkout: Complete' page is displayed with the message 'Thank you for your order!'. |
| Click the 'Back Home' button. | The user is redirected back to the Products page (https://www.saucedemo.com/inventory.html). |

## C298 — Cart State Reset After Completion

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' in First Name, 'Potter' in Last Name, '12345' in Zip/Postal Code, and click 'Continue'. | User is redirected to the 'Checkout: Overview' page. |
| Click the 'Finish' button. | User is redirected to the 'Checkout: Complete!' page showing the 'Thank you for your order!' message. |
| Click the 'Back Home' button. | User is redirected back to the Products page. |
| Observe the Shopping Cart icon in the header. | The shopping cart badge is no longer visible, indicating the cart is empty. |
| Click on the Shopping Cart icon. | The Cart page opens and contains no items. |

## C299 — Browser Back Navigation After Order Completion

**Priority:** Medium
**Type:** Destructive testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' in First Name, 'Potter' in Last Name, '12345' in Zip Code, and click 'Continue'. | The user is redirected to the 'Checkout: Overview' page. |
| Click the 'Finish' button. | The user is redirected to the 'Checkout: Complete' page showing the 'Thank you for your order!' message. |
| Click the browser's 'Back' button. | The user is returned to the 'Checkout: Overview' page, but the cart is empty and the page state reflects that the transaction is no longer active. |
| Click the Finish button again on the Checkout Overview page after returning with the browser Back button. | The application handles the repeated finish action without crashing, freezing, or displaying inconsistent UI. The user is redirected to the Checkout Complete page again, and the cart remains empty. |

## C300 — Direct URL Access to Checkout Complete Without Completed Order

**Priority:** Medium
**Type:** Security testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Manually enter the Checkout Complete URL in the browser address bar: https://www.saucedemo.com/checkout-complete.html and press Enter. | The system prevents access to the completion page; the user is either redirected to an earlier step in the flow (like the Cart or Products page) or an error message is displayed indicating that the checkout must be completed first. |
| Add an item to the cart and navigate to the Cart page. | The item is added and the user is on the cart page. |
| Again, manually enter the Checkout Complete URL in the address bar: https://www.saucedemo.com/checkout-complete.html and press Enter. | The system does not display the 'THANK YOU FOR YOUR ORDER' message; the user is restricted from viewing the final success state without clicking the 'Finish' button on the Overview page. |

## C301 — Standard User Baseline Checkout Success

**Priority:** High
**Type:** Smoke testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' in the First Name field, 'Potter' in the Last Name field, and '12345' in the Zip/Postal Code field. | The fields are populated with the entered text. |
| Click the 'Continue' button. | The user is redirected to the 'Checkout: Overview' page (checkout-step-two.html). |
| Verify that the item description, quantity, price, 'Item total', 'Tax', and 'Total' are displayed and the calculation is correct. | All order details are visible; the 'Total' correctly reflects the sum of 'Item total' and 'Tax'. |
| Click the 'Finish' button. | The user is redirected to the 'Checkout: Complete!' page (checkout-complete.html). |
| Verify the presence of the 'Thank you for your order!' header and the 'Back Home' button. | The confirmation message is clearly displayed, and the 'Back Home' button is visible. |
| Click the 'Back Home' button. | The user is redirected back to the Products page (inventory.html). |

## C302 — Checkout Page Loading Behavior for Performance Glitch User

**Priority:** Medium
**Type:** Performance testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'performance_glitch_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Observe the application behavior after the delay. | The 'Checkout: Your Information' page (checkout-step-one.html) loads successfully after the delay. |
| Enter valid information (First Name: Harry, Last Name: Potter, Zip Code: 12345) and click 'Continue'. | The 'Checkout: Overview' page loads, allowing the user to proceed with the purchase. |

## C303 — Performance Glitch - Overview Page Transition Delay

**Priority:** Medium
**Type:** Performance testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'performance_glitch_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter valid information: First Name 'Harry', Last Name 'Potter', and Zip Code '12345'. | The fields are populated with the entered data. |
| Click the 'Continue' button and observe the transition time to the next page. | There is a noticeable delay before the page changes, but the application does not crash or time out. |
| Verify the state of the application after the delay. | The user is eventually redirected to the 'Checkout: Overview' page (Step Two), and all order details (Item Total, Tax, Total) are displayed correctly. |
| Click the 'Finish' button. | The order is completed successfully, and the 'Checkout: Complete' page is displayed with the confirmation message. |

## C304 — Problem User - Field Input Restriction

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'problem_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' into the 'First Name' field. | The text 'Harry' is visible in the First Name input field. |
| Attempt to enter 'Potter' into the 'Last Name' field. | The 'Last Name' field remains empty or does not accept the input, which is a known defect for the 'problem_user'. |
| Enter '12345' into the 'Zip/Postal Code' field. | The text '12345' is visible in the Zip/Postal Code input field. |
| Click the 'Continue' button. | An error message is displayed stating 'Error: Last Name is required', and the user remains on the 'Checkout: Your Information' page. |

## C305 — Checkout Completion Behavior for Error User

**Priority:** High
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'error_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter valid information (First Name: Harry, Last Name: Potter, Zip Code: 12345) and click 'Continue'. | The 'Checkout: Overview' page (Step Two) is displayed, showing the item total, tax, and total price. |
| Click the 'Finish' button. | The system fails to redirect to the 'Checkout: Complete' page; instead, a functional error occurs (such as the page remaining on the overview or an error message appearing) because the 'error_user' is designed to encounter failures during the final checkout step. |

## C306 — Checkout Pages Visual Consistency for Visual User

**Priority:** Medium
**Type:** Usability testing

**Preconditions:**
- Log in to Sauce Demo as 'visual_user'
- Add any item to the cart.

| Step | Expected Result |
|---|---|
| Navigate to the Cart page and click the 'Checkout' button. | The 'Checkout: Your Information' page (checkout-step-one.html) loads. |
| Inspect the layout of the First Name, Last Name, and Zip/Postal Code input fields and their respective labels. | Visual anomalies are observed, such as the 'Last Name' input field being misaligned or overlapping with other UI elements compared to the standard layout. |
| Enter valid data (First Name: Harry, Last Name: Potter, Zip Code: 12345) and click the 'Continue' button. | The 'Checkout: Overview' page (checkout-step-two.html) loads. |
| Observe the layout of the 'Cancel' and 'Finish' buttons at the bottom of the page. | The 'Finish' button or other UI elements on the overview page show visual inconsistencies or alignment issues specific to the visual_user profile. |

## C308 — Verify checkout cannot be completed with an empty cart

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- User is logged in as standard_user.
- Cart is empty.
- User is on the Cart page: https://www.saucedemo.com/cart.html.

| Step | Expected Result |
|---|---|
| Click the Checkout button. | The application should prevent checkout from starting with an empty cart or display a message that at least one product must be added before checkout. |
| If the application redirects to Checkout: Your Information, enter valid checkout data: First Name Harry, Last Name Potter, Zip Code 12345. | The input fields accept the entered values. |
| Click the 'Continue' button. | The application should prevent the user from proceeding to Checkout Overview with an empty cart or display a validation/error message. |
| If the application redirects to Checkout: Overview, click the Finish button. | The application should not complete checkout with an empty cart and should not display the order confirmation page. |

## C310 — Cancel Button Navigation from Checkout Information Page

**Priority:** Medium
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' in the First Name field, 'Potter' in the Last Name field, and '12345' in the Zip/Postal Code field. | The fields are populated with the entered text. |
| Click the 'Cancel' button located next to the 'Continue' button. | The user is immediately redirected back to the 'Your Cart' page (cart.html). |
| Click the 'Checkout' button again to return to the information form. | The 'Checkout: Your Information' page loads with all input fields (First Name, Last Name, Zip Code) being empty, confirming data was not saved. |

## C311 — Error Message UI Visibility and Updates

**Priority:** Medium
**Type:** Usability testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Leave all fields empty and click the 'Continue' button. | An error message 'Error: First Name is required' appears at the bottom of the form. The message container has a distinct red background, white text, and an 'X' icon is visible in the input fields. |
| Enter 'Harry' into the First Name field and click the 'Continue' button again. | The previous error message is removed and replaced by a new error message: 'Error: Last Name is required'. The red styling and error icons remain consistent. |
| Enter 'Potter' into the Last Name field and click the 'Continue' button again. | The previous error message is removed and replaced by a new error message: 'Error: Postal Code is required'. |
| Click the 'X' button inside the error message container. | The error message container is hidden from the UI. |
| Enter '12345' into the Zip/Postal Code field and click the 'Continue' button. | The user is successfully redirected to the 'Checkout: Overview' page (Step Two), and no error messages are displayed. |

## C313 — Verify checkout form behavior with international characters in name fields

**Priority:** Low
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter international characters into the First Name field (e.g., 'André-François'). | The First Name field accepts and displays the international characters correctly. |
| Enter international characters into the Last Name field (e.g., 'Muñoz-O'Higgins'). | The Last Name field accepts and displays the international characters correctly. |
| Enter a valid numeric value into the Zip/Postal Code field (e.g., '12345') and click the 'Continue' button. | The form is submitted successfully without validation errors, and the user is redirected to the 'Checkout: Overview' page. |
| Review the 'Checkout: Overview' page (if the application displays the user's name) or proceed to click 'Finish'. | The application processes the data without crashing or displaying encoding errors (like '?' or ''). |

## C314 — Zip Code Field Handling with Different Non-Empty Values

**Priority:** Low
**Type:** Functional testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter 'Harry' in the First Name field, 'Potter' in the Last Name field, and '12345' in the Zip/Postal Code field. Click 'Continue'. | The form is accepted and the user is redirected to 'Checkout: Overview' (checkout-step-two.html). |
| Click 'Cancel' to return to the cart, then click 'Checkout' again. Enter valid names and '90210-1234' in the Zip/Postal Code field. Click 'Continue'. | The form is accepted and the user is redirected to 'Checkout: Overview' (checkout-step-two.html). |
| Click 'Cancel' to return to the cart, then click 'Checkout' again. Enter valid names and an alphanumeric code 'SW1A 1AA' in the Zip/Postal Code field. Click 'Continue'. | The form is accepted and the user is redirected to 'Checkout: Overview' (checkout-step-two.html). |
| Click 'Cancel' to return to the cart, then click 'Checkout' again. Enter valid names, leave the Zip/Postal Code field empty, and click 'Continue'. | The form is not submitted and an error message is displayed: 'Error: Postal Code is required'. |

## C316 — Repeated Continue Button Click Handling

**Priority:** Medium
**Type:** Destructive testing

**Preconditions:**
- Log in to https://www.saucedemo.com/ as a 'standard_user'
- Add any item to the cart
- Navigate to the 'Checkout: Your Information' page (https://www.saucedemo.com/checkout-step-one.html

| Step | Expected Result |
|---|---|
| Enter valid data into the form: First Name 'Harry', Last Name 'Potter', and Zip Code '12345'. | The input fields are populated with the provided data. |
| Click the 'Continue' button rapidly multiple times in quick succession. | The application processes the request without crashing or displaying multiple error messages; the user is redirected to the 'Checkout: Overview' page exactly once. |
| Observe the UI behavior during the rapid clicks. | The 'Continue' button should ideally become unresponsive or disabled after the first click to prevent redundant network requests or logic errors. |
