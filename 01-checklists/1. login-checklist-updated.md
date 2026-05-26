# Login Checklist – Sauce Demo

## ✅ Positive scenarios
- [ ] Login with `standard_user` using valid password
- [ ] Login with `problem_user` using valid password
- [ ] Login with `performance_glitch_user` using valid password
- [ ] Login with `error_user` using valid password
- [ ] Login with `visual_user` using valid password
- [ ] Successful redirect to Products page after valid login
- [ ] Session remains active after browser refresh on Products page
- [ ] User can log out from the application
- [ ] User can log in again after logout

---

## ❌ Negative scenarios
- [ ] Login with valid username and invalid password
- [ ] Login with non-existing username
- [ ] Login with empty username field
- [ ] Login with empty password field
- [ ] Login with both username and password fields empty
- [ ] Login with `locked_out_user` is blocked
- [ ] Username case sensitivity is handled correctly
- [ ] Password case sensitivity is handled correctly
- [ ] Username with leading/trailing spaces is handled correctly
- [ ] Password with leading/trailing spaces is handled correctly
- [ ] Whitespace-only username is rejected
- [ ] Whitespace-only password is rejected
- [ ] Proper error message is displayed for invalid credentials
- [ ] Error highlighting is displayed after failed login attempt

---

## ✨ UI / Usability
- [ ] Username input field is visible
- [ ] Password input field is visible
- [ ] Login button is visible and clickable
- [ ] Password field masks entered characters
- [ ] Error message is readable and clear
- [ ] Error message can be dismissed using the close button
- [ ] Login form remains usable on different screen sizes
- [ ] Keyboard navigation works through Username, Password, and Login button
- [ ] Login form can be submitted using Enter key

---

## 🛡️ Security / Session
- [ ] Password is not displayed in plain text
- [ ] User cannot log in without credentials
- [ ] Direct access to Products page without active session is blocked
- [ ] Browser Back button does not restore authorized Products page after logout
- [ ] User loses access to protected pages after manual storage/session clearance
- [ ] Special characters in credentials are treated as plain text
- [ ] SQL-like input in credentials does not bypass authentication
- [ ] Unicode and multi-byte characters do not break login form behavior

---

## ⚡ Performance / Destructive
- [ ] Login with `performance_glitch_user` shows noticeable delay but completes successfully
- [ ] Extremely long username and password values do not crash the page
- [ ] Rapid repeated login submissions do not break application behavior
- [ ] Login attempt during network interruption does not crash the application
