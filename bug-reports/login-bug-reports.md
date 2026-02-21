# Login Bug Reports – Sauce Demo

## BUG-01: Error message is not cleared after successful login
**Severity:** Minor  
**Priority:** Medium  

**Preconditions:**  
User is on Login page and previously entered invalid credentials.

**Steps to Reproduce:**  
1. Enter invalid username  
2. Enter invalid password  
3. Click Login  
4. Enter valid username  
5. Enter valid password  
6. Click Login  

**Expected Result:**  
User is logged in successfully and error message is not displayed.

**Actual Result:**  
User is logged in, but previous error message remains visible.

---

## BUG-02: Login button is clickable with empty fields
**Severity:** Minor  
**Priority:** Low  

**Preconditions:**  
User is on Login page.

**Steps to Reproduce:**  
1. Leave username field empty  
2. Leave password field empty  
3. Click Login  

**Expected Result:**  
Login button should be disabled or validation message should appear.

**Actual Result:**  
Login button is clickable.

---

## BUG-03: Error message text is not user-friendly
**Severity:** Trivial  
**Priority:** Low  

**Preconditions:**  
User is on Login page.

**Steps to Reproduce:**  
1. Enter invalid credentials  
2. Click Login  

**Expected Result:**  
Clear and user-friendly error message is displayed.

**Actual Result:**  
Error message is too generic and does not explain the issue clearly.
