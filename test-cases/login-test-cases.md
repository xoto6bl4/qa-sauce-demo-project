# Login Test Cases – Sauce Demo

| ID | Title | Preconditions | Steps | Expected Result |
|----|-------|---------------|-------|-----------------|
| TC-01 | Login with valid credentials | User is on Login page | 1. Enter valid username<br>2. Enter valid password<br>3. Click Login | User is successfully logged in and redirected to Products page |
| TC-02 | Login with invalid username | User is on Login page | 1. Enter invalid username<br>2. Enter valid password<br>3. Click Login | Error message is displayed |
| TC-03 | Login with invalid password | User is on Login page | 1. Enter valid username<br>2. Enter invalid password<br>3. Click Login | Error message is displayed |
| TC-04 | Login with empty username field | User is on Login page | 1. Leave username empty<br>2. Enter password<br>3. Click Login | Error message is displayed |
| TC-05 | Login with empty password field | User is on Login page | 1. Enter username<br>2. Leave password empty<br>3. Click Login | Error message is displayed |
| TC-06 | Login with both fields empty | User is on Login page | 1. Leave username empty<br>2. Leave password empty<br>3. Click Login | Error message is displayed |
| TC-07 | Password field masks input | User is on Login page | 1. Type password | Password characters are hidden |
| TC-08 | Logout from application | User is logged in | 1. Open menu<br>2. Click Logout | User is logged out and redirected to Login page |
| TC-09 | Login button is clickable | User is on Login page | 1. Hover and click Login | Button responds to click |
| TC-10 | Error message disappears after successful login | User previously saw error | 1. Enter valid credentials<br>2. Click Login | Error message is not displayed |
