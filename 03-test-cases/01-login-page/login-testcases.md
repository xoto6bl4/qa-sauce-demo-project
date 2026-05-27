# SauceDemo Auth Test Cases

## Summary

| ID | Title | Type | Priority |
|---|---|---|---|
| C129 | Successful Login - Standard User | Smoke & Sanity | High |
| C130 | Successful Login - Problem User | Functional | Medium |
| C131 | Successful Login - Performance Glitch User | Functional | Medium |
| C132 | Successful Login - Error User | Functional | Medium |
| C133 | Successful Login - Visual User | Functional | Medium |
| C134 | Session Persistence - Browser Refresh | Functional | Medium |
| C135 | Successful Logout | Smoke & Sanity | High |
| C136 | Re-authentication After Logout | Functional | High |
| C137 | Failed Login - Invalid Password | Functional | High |
| C138 | Unauthorized Access - Protected Route Redirection | Functional | High |
| C143 | Username Case Sensitivity | Functional | Medium |
| C144 | Password Case Sensitivity | Functional | Medium |
| C145 | Username Whitespace Handling | Functional | Medium |
| C146 | Password Whitespace Handling | Functional | Medium |
| C148 | Login Attempt with Extremely Long Input Values | Performance | Low |
| C149 | Login Attempt with Empty Credentials | Functional | High |
| C150 | Login Attempt with Missing Password | Functional | High |
| C151 | Login Attempt with Missing Username | Functional | Medium |
| C152 | Login Attempt with Non-Existent User | Functional | High |
| C154 | Login Attempt with Locked Out User | Functional | High |
| C155 | Error Highlighting after Failed Login Attempt | Functional | Medium |
| C158 | Login Attempt with Special Characters in Credentials | Functional | Medium |
| C163 | Session Security - Back Button After Logout | Security | High |
| C164 | UI Security - Password Masking | Security | High |
| C165 | Login Page Responsiveness on Different Screen Sizes | Usability | Low |
| C166 | UI Behavior - Error Message Dismissal | Usability | Medium |
| C167 | Verify Keyboard Navigation and Submission | Accessibility | Medium |
| C168 | Session Management - Manual Storage Clearance | Security | Medium |
| C170 | Login Button Behavior with Invalid Input | Functional | Medium |
| C171 | Login Attempt during Network Interruption | Destructive | Medium |
| C174 | Login Attempt with Whitespace-Only Username | Functional | Medium |
| C175 | Login Attempt with Whitespace-Only Password | Functional | Medium |
| C179 | Unicode and Multi-byte Character Support | Functional | Medium |
| C185 | Rapid Login Submission with Long Input Values | Performance | Medium |

## Detailed Test Cases

<details>
<summary><strong>C129: Successful Login - Standard User</strong></summary>

**Type:** Smoke & Sanity  
**Priority:** High  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter 'standard_user' into the Username input field.
3. Enter 'secret_sauce' into the Password input field.
4. Click the 'Login' button.
5. Observe the page header and product list.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username field accepts the input and displays 'standard_user'.
3. The password field accepts the input and masks the characters for security.
4. The user is successfully authenticated and redirected to the Inventory page (URL contains '/inventory.html').
5. The 'Products' title is visible, and the shopping cart icon is displayed in the upper right corner, confirming a successful session start.

</details>

<details>
<summary><strong>C130: Successful Login - Problem User</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter 'problem_user' into the Username field.
3. Enter 'secret_sauce' into the Password field.
4. Click the 'Login' button.
5. Verify the presence of the 'Products' title and the shopping cart icon on the inventory page.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username 'problem_user' is entered into the field.
3. The password is masked as it is entered into the field.
4. The user is successfully authenticated and redirected to the inventory page (https://www.saucedemo.com/inventory.html).
5. The 'Products' title and shopping cart icon are visible, confirming the user is on the main dashboard.

</details>

<details>
<summary><strong>C131: Successful Login - Performance Glitch User</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter 'performance_glitch_user' into the username field.
3. Enter 'secret_sauce' into the password field.
4. Click the 'Login' button.
5. Observe the page redirection after the delay.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username field accepts the input.
3. The password field accepts the input and masks the characters.
4. The system processes the login request. A noticeable delay (approximately 5 seconds) may occur due to the specific user profile characteristics.
5. The user is successfully redirected to the Inventory page (https://www.saucedemo.com/inventory.html) and the product list is visible.

</details>

<details>
<summary><strong>C132: Successful Login - Error User</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter 'error_user' into the Username input field.
3. Enter 'secret_sauce' into the Password input field.
4. Click the 'Login' button.
5. Verify the presence of the main product area and the shopping cart icon.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username field is populated with the text 'error_user'.
3. The password field is populated, and the characters are masked for security.
4. The user is successfully authenticated and redirected to the inventory page (URL contains '/inventory.html').
5. The inventory page is visible, confirming a successful login session for the 'error_user'.

</details>

<details>
<summary><strong>C133: Successful Login - Visual User</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter 'visual_user' into the Username input field.
3. Enter 'secret_sauce' into the Password input field.
4. Click the 'Login' button.
5. Observe the inventory page layout and header.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username field accepts the input 'visual_user'.
3. The password field accepts the input and masks the characters for security.
4. The user is successfully authenticated and redirected to the inventory page (URL: https://www.saucedemo.com/inventory.html).
5. The 'Products' title is visible, and the shopping cart icon is displayed, confirming a successful session for the visual_user.

</details>

<details>
<summary><strong>C134: Session Persistence - Browser Refresh</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter valid credentials (e.g., Username: 'standard_user', Password: 'secret_sauce') and click the 'Login' button.
3. Perform a browser refresh (F5 or Refresh button) while on the Inventory page.
4. Verify that the 'Products' title and the shopping cart icon are still visible and accessible.

**Expected Result:**

1. Login page is displayed successfully with username and password fields.
2. User is successfully authenticated and redirected to the Inventory page (https://www.saucedemo.com/inventory.html).
3. The page reloads successfully; the user remains logged in and is still on the Inventory page.
4. UI elements are present, confirming the session persisted and the user was not redirected back to the login page.

</details>

<details>
<summary><strong>C135: Successful Logout</strong></summary>

**Type:** Smoke & Sanity  
**Priority:** High  

**Steps:**

1. Navigate to https://www.saucedemo.com/ and log in using valid credentials (e.g., standard_user / secret_sauce).
2. Click on the 'Burger Menu' icon (three horizontal lines) located at the top-left corner of the header.
3. Click on the 'Logout' link within the side navigation menu.
4. Observe the current URL and the page content.
5. Attempt to navigate back to the inventory page by manually entering the URL https://www.saucedemo.com/inventory.html in the browser address bar.

**Expected Result:**

1. User is successfully logged in and redirected to the Inventory page (https://www.saucedemo.com/inventory.html).
2. The side navigation menu expands and becomes visible to the user.
3. The user is immediately logged out of the application.
4. The user is redirected to the login page (https://www.saucedemo.com/); the login form is visible, and the username/password fields are empty.
5. Access is denied; the user remains on or is redirected back to the login page, ideally showing an error message indicating they must be logged in.

</details>

<details>
<summary><strong>C136: Re-authentication After Logout</strong></summary>

**Type:** Functional  
**Priority:** High  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter 'standard_user' in the Username field and 'secret_sauce' in the Password field.
3. Click the 'Login' button.
4. Click on the 'Burger Menu' icon in the top left corner and select 'Logout'.
5. Enter 'standard_user' and 'secret_sauce' again and click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with empty Username and Password fields.
2. The input fields accept the credentials.
3. The user is successfully authenticated and redirected to the Inventory page (https://www.saucedemo.com/inventory.html).
4. The user is logged out and redirected back to the Login page. Access to the Inventory page is restricted.
5. The user is successfully re-authenticated and redirected back to the Inventory page.

</details>

<details>
<summary><strong>C137: Failed Login - Invalid Password</strong></summary>

**Type:** Functional  
**Priority:** High  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter a valid username (e.g., 'standard_user') into the Username field.
3. Enter an incorrect password (e.g., 'wrong_sauce') into the Password field.
4. Click the 'Login' button.
5. Observe the URL and the state of the input fields.

**Expected Result:**

1. The login page is displayed with empty 'Username' and 'Password' fields.
2. The username is correctly entered into the field.
3. The password field displays masked characters.
4. The user remains on the login page. A red error message is displayed stating: 'Epic sadface: Username and password do not match any user in this service'.
5. The URL remains 'https://www.saucedemo.com/' and the input fields are highlighted with error icons (X).

</details>

<details>
<summary><strong>C138: Unauthorized Access - Protected Route Redirection</strong></summary>

**Type:** Functional  
**Priority:** High  

**Steps:**

1. Open the browser and ensure no active session exists (clear cookies/cache if necessary).
2. Navigate directly to the inventory page URL: https://www.saucedemo.com/inventory.html
3. Observe the page redirection and the UI state.
4. Check for the presence of an error message on the login form.

**Expected Result:**

1. Browser is open and no previous session data for saucedemo.com is stored.
2. The system identifies the lack of an active authentication token/session.
3. The user is automatically redirected back to the login page (https://www.saucedemo.com/).
4. An error message is displayed stating: 'Epic sadface: You can only access '/inventory.html' after you are logged in.'

</details>

<details>
<summary><strong>C143: Username Case Sensitivity</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the SauceDemo login page: https://www.saucedemo.com/
2. Enter the valid username in uppercase: 'STANDARD_USER'.
3. Enter the valid password: 'secret_sauce'.
4. Click the 'Login' button.
5. Clear the username field and enter the username in mixed case: 'Standard_User'.
6. Click the 'Login' button.
7. Clear the username field and enter the correct lowercase username: 'standard_user'.
8. Click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The username field displays the text in uppercase as entered.
3. The password field displays masked characters.
4. Login fails. An error message is displayed: 'Epic sadface: Username and password do not match any user in this service'.
5. The username field displays 'Standard_User'.
6. Login fails. The error message 'Epic sadface: Username and password do not match any user in this service' remains or reappears.
7. The username field displays 'standard_user'.
8. Login is successful. The user is redirected to the inventory page (https://www.saucedemo.com/inventory.html).

</details>

<details>
<summary><strong>C144: Password Case Sensitivity</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Swag Labs login page: https://www.saucedemo.com/
2. Enter a valid username (e.g., 'standard_user') into the Username field.
3. Enter the valid password but with incorrect casing (e.g., 'SECRET_SAUCE') into the Password field.
4. Click the 'Login' button.
5. Clear the Password field and enter the password with a different incorrect casing (e.g., 'Secret_sauce').
6. Click the 'Login' button.
7. Clear the Password field and enter the correct password with exact casing: 'secret_sauce'.
8. Click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The username 'standard_user' is entered into the field.
3. The password field masks the input characters.
4. The user is not logged in. An error message appears stating: 'Epic sadface: Username and password do not match any user in this service'.
5. The password field is updated with the new string.
6. The user remains on the login page. The error message 'Epic sadface: Username and password do not match any user in this service' is displayed.
7. The correct password is typed into the field.
8. The login is successful, and the user is redirected to the inventory page (https://www.saucedemo.com/inventory.html).

</details>

<details>
<summary><strong>C145: Username Whitespace Handling</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter the username ' standard_user' (with a leading space) and the valid password 'secret_sauce'. Click the 'Login' button.
3. Clear the fields and enter the username 'standard_user ' (with a trailing space) and the valid password 'secret_sauce'. Click the 'Login' button.
4. Clear the fields and enter the username 'standard_user' (no spaces) and the valid password 'secret_sauce'. Click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The system should either log the user in (if trimming is implemented) or display an error message: 'Epic sadface: Username and password do not match any user in this service' (if spaces are treated as literal characters).
3. The system should either log the user in (if trimming is implemented) or display an error message: 'Epic sadface: Username and password do not match any user in this service' (if spaces are treated as literal characters).
4. The user is successfully authenticated and redirected to the inventory page (https://www.saucedemo.com/inventory.html).

</details>

<details>
<summary><strong>C146: Password Whitespace Handling</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter a valid username (e.g., 'standard_user') into the Username field.
3. Enter the valid password with an added leading space (e.g., ' secret_sauce') into the Password field.
4. Click the 'Login' button.
5. Clear the Password field and enter the valid password with an added trailing space (e.g., 'secret_sauce ').
6. Click the 'Login' button.
7. Clear the Password field and enter the exact valid password without any spaces ('secret_sauce').
8. Click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The username is entered correctly into the field.
3. The password field displays masked characters corresponding to the input length.
4. Login fails and an error message 'Epic sadface: Username and password do not match any user in this service' is displayed, indicating the leading space was treated as a literal character.
5. The password field is cleared and the new input is accepted.
6. Login fails and the error message 'Epic sadface: Username and password do not match any user in this service' is displayed, indicating the trailing space was treated as a literal character.
7. The correct password is entered.
8. The user is successfully authenticated and redirected to the inventory page (https://www.saucedemo.com/inventory.html).

</details>

<details>
<summary><strong>C148: Login Attempt with Extremely Long Input Values</strong></summary>

**Type:** Performance  
**Priority:** Low  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Prepare a string of 10,000+ characters (e.g., using a string generator or repeating 'A').
3. Paste the extreme length string into the 'Username' field.
4. Paste the extreme length string into the 'Password' field.
5. Click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with the username and password fields visible.
2. Test data is ready for input.
3. The field accepts the input without the browser freezing; the UI layout remains intact (no horizontal overflow or broken containers).
4. The field masks the input correctly; the UI remains responsive.
5. The system processes the request and returns a standard 'Username and password do not match any user in this service' error message; the page does not crash (e.g., HTTP 500 or browser 'Aw, Snap' error).

</details>

<details>
<summary><strong>C149: Login Attempt with Empty Credentials</strong></summary>

**Type:** Functional  
**Priority:** High  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Ensure both the 'Username' and 'Password' input fields are empty.
3. Click the 'Login' button.
4. Observe the error message displayed on the login form.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. No text or characters are present in either input field.
3. The user remains on the login page (URL does not change to /inventory.html).
4. An error message appears stating: 'Epic sadface: Username is required'. The input fields may be highlighted with error icons (red 'X').

</details>

<details>
<summary><strong>C150: Login Attempt with Missing Password</strong></summary>

**Type:** Functional  
**Priority:** High  

**Steps:**

1. Navigate to the SauceDemo login page: https://www.saucedemo.com/
2. Enter a valid username (e.g., 'standard_user') into the Username field.
3. Leave the Password field completely empty.
4. Click the 'Login' button.
5. Observe the error message displayed on the login form.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The username is correctly entered into the field.
3. The password field remains blank.
4. The user is not redirected; they remain on the login page.
5. An error message appears stating: 'Epic sadface: Password is required'. Both input fields may be highlighted with error icons (red 'X').

</details>

<details>
<summary><strong>C151: Login Attempt with Missing Username</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Leave the 'Username' input field empty.
3. Enter a valid password (e.g., 'secret_sauce') into the 'Password' input field.
4. Click the 'Login' button.
5. Observe the error message displayed on the page.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The 'Username' field remains empty and no validation error is shown yet.
3. The password characters are masked for security.
4. The user is not logged in and remains on the login page.
5. An error message appears stating: 'Epic sadface: Username is required'. The input fields may be highlighted in red to indicate a validation error.

</details>

<details>
<summary><strong>C152: Login Attempt with Non-Existent User</strong></summary>

**Type:** Functional  
**Priority:** High  

**Steps:**

1. Navigate to the SauceDemo login page: https://www.saucedemo.com/
2. Enter a non-existent username (e.g., 'unknown_user') into the Username field.
3. Enter a random password (e.g., 'wrong_password') into the Password field.
4. Click the 'Login' button.
5. Refresh the browser page.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username 'unknown_user' is entered into the field.
3. The password 'wrong_password' is entered into the field (masked).
4. The user remains on the login page. An error message is displayed: 'Epic sadface: Username and password do not match any user in this service'.
5. The error message disappears, and the login fields are cleared, confirming no session was created.

</details>

<details>
<summary><strong>C154: Login Attempt with Locked Out User</strong></summary>

**Type:** Functional  
**Priority:** High  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter 'locked_out_user' into the Username input field.
3. Enter 'secret_sauce' into the Password input field.
4. Click the 'Login' button.
5. Observe the text content of the error message.
6. Verify that no redirection to the inventory page occurs.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username 'locked_out_user' is entered correctly into the field.
3. The password 'secret_sauce' is entered (masked) into the field.
4. The user remains on the login page. A red error message container appears at the bottom of the form.
5. The error message displays exactly: 'Epic sadface: Sorry, this user has been locked out.'
6. The URL remains 'https://www.saucedemo.com/' and the inventory page is not accessible.

</details>

<details>
<summary><strong>C155: Error Highlighting after Failed Login Attempt</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Leave both the 'Username' and 'Password' fields empty and click the 'Login' button.
3. Refresh the page and enter 'standard_user' in the username field but leave the password field empty. Click 'Login'.
4. Enter an invalid username (e.g., 'invalid_user') and an invalid password (e.g., 'wrong_pass') and click 'Login'.
5. Click the 'X' (close) button on the error message container.

**Expected Result:**

1. The login page loads successfully; username and password fields are displayed with default styling (no error indicators).
2. An error message appears. Both the 'Username' and 'Password' input fields are highlighted with a red bottom border and a red 'X' icon is displayed inside the right edge of both input fields.
3. The error message 'Epic sadface: Password is required' is displayed. Both input fields remain highlighted with red borders and error icons, indicating a validation failure state for the form.
4. The error message 'Epic sadface: Username and password do not match any user in this service' is displayed. Both input fields are visually marked with red error icons and red borders.
5. The error message disappears, and the red highlighting/error icons are removed from the input fields, returning them to their default state.

</details>

<details>
<summary><strong>C158: Login Attempt with Special Characters in Credentials</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter a username containing special characters and SQL patterns (e.g., ' OR '1'='1) into the Username field.
3. Enter a password containing symbols and special characters (e.g., !@#$%^&*()_+) into the Password field.
4. Click the 'Login' button.
5. Clear the fields and enter a valid username (standard_user) and a password containing special characters (e.g., alert(1)).
6. Click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The characters are accepted and displayed in the input field as literal text.
3. The characters are accepted and masked in the password field.
4. The system treats the input as a literal string and does not execute any code; an error message 'Epic sadface: Username and password do not match any user in this service' is displayed.
5. The input is treated as a string; no script execution occurs.
6. The user remains on the login page and an error message 'Epic sadface: Username and password do not match any user in this service' is displayed.

</details>

<details>
<summary><strong>C163: Session Security - Back Button After Logout</strong></summary>

**Type:** Security  
**Priority:** High  

**Steps:**

1. Navigate to https://www.saucedemo.com/ and log in using valid credentials (e.g., standard_user / secret_sauce).
2. Click on the 'Burger Menu' icon in the top left corner and select 'Logout'.
3. Click the browser's 'Back' button.
4. If the browser displays a cached version of the Inventory page, attempt to click on a product link or add an item to the cart.

**Expected Result:**

1. User is successfully logged in and redirected to the Inventory page (https://www.saucedemo.com/inventory.html).
2. User is logged out and redirected back to the Login page (https://www.saucedemo.com/). Session is invalidated.
3. The user should not be able to access the Inventory page. The application should either remain on the Login page or redirect the user back to the Login page immediately.
4. The application must prevent any authenticated actions and redirect the user to the Login page with an error message indicating that the session has expired or that the user must be logged in.

</details>

<details>
<summary><strong>C164: UI Security - Password Masking</strong></summary>

**Type:** Security  
**Priority:** High  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Locate the password input field and inspect its HTML 'type' attribute.
3. Enter a valid password (e.g., 'secret_sauce') into the password field.
4. Attempt to copy the masked text from the password field and paste it into a text editor.

**Expected Result:**

1. The login page loads successfully, displaying the username and password input fields.
2. The 'type' attribute of the password input field is set to 'password'.
3. The characters entered are masked (displayed as dots, bullets, or asterisks) and are not visible as plain text.
4. The system should either prevent copying from the password field or, if pasted, ensure the plain text password is not exposed via the clipboard in a way that bypasses standard UI masking.

</details>

<details>
<summary><strong>C165: Login Page Responsiveness on Different Screen Sizes</strong></summary>

**Type:** Usability  
**Priority:** Low  

**Steps:**

1. Navigate to https://www.saucedemo.com/ on a standard desktop browser (e.g., 1920x1080).
2. Resize the browser window to a tablet resolution (e.g., width 768px).
3. Resize the browser window to a mobile resolution (e.g., width 375px) or use browser developer tools to emulate a mobile device.
4. Change the device orientation from portrait to landscape in mobile/tablet view.
5. Verify the visibility of the 'Accepted usernames' and 'Password for all users' information sections at the bottom of the page across all resolutions.

**Expected Result:**

1. The login form is centered, all elements are clearly visible, and the background branding image is displayed correctly without overlapping text.
2. The layout adjusts gracefully; the login container remains centered, and input fields maintain appropriate padding and width relative to the screen size.
3. The login form stacks or scales appropriately; the 'Login' button remains easily clickable (tappable), and no horizontal scrollbar appears.
4. The UI adapts to the new orientation immediately; all form fields remain accessible and are not cut off by the viewport boundaries.
5. The informational text remains legible and wraps correctly on smaller screens without breaking the page layout.

</details>

<details>
<summary><strong>C166: UI Behavior - Error Message Dismissal</strong></summary>

**Type:** Usability  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter invalid credentials (e.g., 'invalid_user' / 'wrong_password') and click the 'Login' button.
3. Click the 'X' button located within the error message container.
4. Enter another set of invalid credentials and click 'Login' to trigger the error message again.
5. Without clicking the 'X' button, enter valid credentials ('standard_user' / 'secret_sauce') and click 'Login'.

**Expected Result:**

1. The login page loads successfully with the username, password, and login button visible.
2. An error message container appears at the bottom of the form with a red background and an 'X' (close) button.
3. The error message container is dismissed and is no longer visible on the UI.
4. The error message container reappears.
5. The error message disappears immediately upon the new login attempt, and the user is successfully redirected to the inventory page.

</details>

<details>
<summary><strong>C167: Verify Keyboard Navigation and Submission</strong></summary>

**Type:** Accessibility  
**Priority:** Medium  

**Steps:**

1. Navigate to the SauceDemo login page: https://www.saucedemo.com/
2. Press the 'Tab' key on the keyboard.
3. Type 'standard_user' into the 'Username' field and press 'Tab' again.
4. Type 'secret_sauce' into the 'Password' field and press 'Tab' again.
5. With the focus on the 'Login' button, press the 'Enter' key.
6. Logout and return to the login page, then enter valid credentials and press 'Enter' while the focus is still inside the 'Password' text field.

**Expected Result:**

1. The login page loads successfully with the cursor focus initially outside the input fields or at the start of the document.
2. The focus moves to the 'Username' input field, indicated by a visual focus ring or cursor.
3. The focus moves from the 'Username' field to the 'Password' input field.
4. The focus moves from the 'Password' field to the 'Login' button.
5. The form is submitted, and the user is successfully redirected to the inventory page (https://www.saucedemo.com/inventory.html).
6. The form is submitted successfully, and the user is redirected to the inventory page (standard behavior for form submission via Enter key).

</details>

<details>
<summary><strong>C168: Session Management - Manual Storage Clearance</strong></summary>

**Type:** Security  
**Priority:** Medium  

**Steps:**

1. Navigate to https://www.saucedemo.com/ and log in using valid credentials (e.g., standard_user / secret_sauce).
2. Open the browser's Developer Tools (F12), navigate to the 'Application' or 'Storage' tab, and clear all Cookies, Local Storage, and Session Storage for the site.
3. Manually refresh the current page (Inventory page).
4. Attempt to navigate directly to the protected URL: https://www.saucedemo.com/inventory.html by typing it into the address bar.

**Expected Result:**

1. User is successfully logged in and redirected to the Inventory page (https://www.saucedemo.com/inventory.html).
2. Storage data is successfully removed; no session identifiers remain in the browser.
3. The application detects the absence of session data and redirects the user back to the Login page.
4. Access is denied; the user is redirected to the Login page, and the protected content is not displayed.

</details>

<details>
<summary><strong>C170: Login Button Behavior with Invalid Input</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the SauceDemo login page: https://www.saucedemo.com/
2. Ensure both the 'Username' and 'Password' input fields are empty.
3. Click the 'Login' button without entering any data.
4. Enter a valid username (e.g., 'standard_user') but leave the 'Password' field empty.
5. Click the 'Login' button.

**Expected Result:**

1. The login page loads successfully with the username and password fields visible and empty.
2. No text is present in either input field.
3. The system provides immediate visual feedback: error icons appear in the input fields, the fields are highlighted (e.g., in red), and an error message 'Epic sadface: Username is required' is displayed.
4. The 'Username' field error state may clear, but clicking 'Login' triggers visual feedback for the 'Password' field.
5. The system provides visual feedback indicating the password is required, such as an error message 'Epic sadface: Password is required' and red highlighting on the password field.

</details>

<details>
<summary><strong>C171: Login Attempt during Network Interruption</strong></summary>

**Type:** Destructive  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter valid credentials (e.g., 'standard_user' and 'secret_sauce').
3. Simulate a network disconnection (e.g., disable Wi-Fi, unplug Ethernet, or use Browser DevTools to set Network Throttling to 'Offline').
4. Click the 'Login' button while the network is disconnected.
5. Restore the network connection.
6. Click the 'Login' button again without refreshing the page.

**Expected Result:**

1. The login page loads successfully with the username, password, and login button visible.
2. The credentials are typed into the respective input fields.
3. The browser indicates an offline status or no active internet connection.
4. The application may continue to work using already loaded client-side resources. Since Sauce Demo is a demo application, login, cart, and checkout actions may still be available without active network connection after the page has been loaded.
5. The network connection is active again.
6. The login request is processed successfully, and the user is redirected to the inventory page (https://www.saucedemo.com/inventory.html).

</details>

<details>
<summary><strong>C174: Login Attempt with Whitespace-Only Username</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the SauceDemo login page: https://www.saucedemo.com/
2. Enter five spaces ( ) into the 'Username' input field.
3. Enter the valid password 'secret_sauce' into the 'Password' input field.
4. Click the 'Login' button.
5. Observe the error message displayed on the login form.

**Expected Result:**

1. The login page loads successfully with the username, password fields, and login button visible.
2. The spaces are accepted into the field without being automatically trimmed or blocked during entry.
3. The password field displays masked characters.
4. The user is not logged in and remains on the login page.
5. An error message appears stating: 'Epic sadface: Username and password do not match any user in this service'.

</details>

<details>
<summary><strong>C175: Login Attempt with Whitespace-Only Password</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter a valid username (e.g., 'standard_user') into the Username field.
3. Enter a string consisting only of spaces (e.g., ' ') into the Password field.
4. Click the 'Login' button.
5. Observe the URL and page content.

**Expected Result:**

1. The login page loads successfully, displaying the username field, password field, and login button.
2. The username 'standard_user' is correctly entered into the field.
3. The password field accepts the input (masked as dots/asterisks).
4. The user is not logged in. An error message is displayed stating: 'Epic sadface: Password is required' or 'Epic sadface: Username and password do not match any user in this service'.
5. The URL remains 'https://www.saucedemo.com/' and the user stays on the login page.

</details>

<details>
<summary><strong>C179: Unicode and Multi-byte Character Support</strong></summary>

**Type:** Functional  
**Priority:** Medium  

**Steps:**

1. Navigate to the Sauce Demo login page: https://www.saucedemo.com/
2. Enter a username containing Unicode characters (e.g., 'ユーザー' or '🚀_user') and a valid password ('secret_sauce').
3. Click the 'Login' button.
4. Clear the fields and enter a valid username ('standard_user') and a password containing multi-byte characters (e.g., 'пароль123' or '🔑secret').
5. Click the 'Login' button.
6. Verify that the UI layout remains intact and no server-side errors (500 Internal Server Error) are triggered by the special character submission.

**Expected Result:**

1. The login page loads successfully with the username and password fields visible.
2. The characters are displayed correctly in the input field without encoding errors.
3. The system remains on the login page and displays an error message: 'Epic sadface: Username and password do not match any user in this service'.
4. The password field masks the input, but the character count/length is handled correctly.
5. The system remains on the login page and displays an error message: 'Epic sadface: Username and password do not match any user in this service'.
6. The UI components (error container, buttons, inputs) are aligned correctly, and the application remains responsive.

</details>

<details>
<summary><strong>C185: Rapid Login Submission with Long Input Values</strong></summary>

**Type:** Performance  
**Priority:** Medium  

**Steps:**

1. Navigate to the SauceDemo login page: https://www.saucedemo.com/
2. Enter a string of 500+ characters into the 'Username' field.
3. Enter a string of 500+ characters into the 'Password' field.
4. Rapidly click the 'Login' button 10 times in quick succession (less than 5 seconds).
5. Observe the error message displayed after the rapid submission attempts.

**Expected Result:**

1. The login page loads successfully with the username and password fields visible.
2. The field accepts the long input without UI distortion or browser freezing.
3. The field accepts the long input, masking the characters as expected.
4. The application remains responsive; it does not crash, hang, or throw a 500-series server error.
5. An error message 'Epic sadface: Username and password do not match any user in this service' is displayed, and the user remains on the login page.

</details>
