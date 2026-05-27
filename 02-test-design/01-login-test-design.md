# Login Test Design – Sauce Demo

## 🎯 Feature: Login Form

### Page URL

`https://www.saucedemo.com`

### Input Fields

- Username
- Password

---

## 🔹 Equivalence Partitioning

### Username Field

| Class Type | Test Data | Expected Result |
|---|---|---|
| Valid class | Existing valid username, e.g. `standard_user` | User can log in with the correct password |
| Invalid class | Non-existing username, e.g. `unknown_user` | Login is rejected and an error message is displayed |
| Invalid class | Empty username | Login is rejected and `Username is required` error is displayed |
| Invalid class | Username with leading/trailing spaces, e.g. ` standard_user ` | Login is rejected if spaces are treated as part of the username |
| Invalid class | Username with special characters, e.g. `!@#$%^&*()` | Login is rejected and the application remains stable |
| Invalid class | Unicode or multi-byte username, e.g. `ユーザー`, `🚀_user` | Login is rejected and the application remains stable |
| Invalid class | Extremely long username value | Login is rejected or handled safely without UI crash or layout breaking |

---

### Password Field

| Class Type | Test Data | Expected Result |
|---|---|---|
| Valid class | Correct password: `secret_sauce` | User can log in with a valid username |
| Invalid class | Incorrect password, e.g. `wrong_sauce` | Login is rejected and an error message is displayed |
| Invalid class | Empty password | Login is rejected and `Password is required` error is displayed |
| Invalid class | Password with leading/trailing spaces, e.g. ` secret_sauce ` | Login is rejected if spaces are treated as part of the password |
| Invalid class | Password with special characters, e.g. `!@#$%^&*()` | Login is rejected and the application remains stable |
| Invalid class | Unicode or multi-byte password, e.g. `пароль123`, `🔑secret` | Login is rejected and the application remains stable |
| Invalid class | Extremely long password value | Login is rejected or handled safely without UI crash or layout breaking |

---

## 🔹 User Role / Account State Partitioning

| User Type | Test Data | Expected Result |
|---|---|---|
| Standard user | `standard_user / secret_sauce` | User logs in successfully and is redirected to Products page |
| Problem user | `problem_user / secret_sauce` | User logs in successfully, but product-related issues may appear after login |
| Performance glitch user | `performance_glitch_user / secret_sauce` | User logs in successfully, but Products page loading is noticeably delayed |
| Error user | `error_user / secret_sauce` | User logs in successfully, but some functional issues may appear after login |
| Visual user | `visual_user / secret_sauce` | User logs in successfully, but visual layout issues may appear after login |
| Locked out user | `locked_out_user / secret_sauce` | Login is blocked and locked out user error is displayed |

---

## 🔹 Negative Testing

| Scenario | Expected Result |
|---|---|
| Empty username and empty password | Login is blocked and `Username is required` error is displayed |
| Valid username with empty password | Login is blocked and `Password is required` error is displayed |
| Empty username with valid password | Login is blocked and `Username is required` error is displayed |
| Valid username with invalid password | Login is blocked and credentials mismatch error is displayed |
| Invalid username with valid password | Login is blocked and credentials mismatch error is displayed |
| Locked out user credentials | Login is blocked and locked out user error is displayed |

---

## 🔹 Security Checks

| Scenario | Expected Result |
|---|---|
| Password input masking | Password characters are hidden in the input field |
| Direct access to protected page without login | User is redirected to Login page |
| Browser Back button after logout | Protected page is not restored as an active authenticated session |
| Manual storage/session clearance | User loses access to protected pages after session data is removed |
| Special characters or SQL-like input in login fields | Input is treated as plain text and does not break application behavior |

---

## 🔹 Destructive / Edge Case Checks

| Scenario | Expected Result |
|---|---|
| Extremely long username and password values | Application remains stable and does not crash |
| Rapid repeated clicks on Login button | Application remains responsive and does not create inconsistent session behavior |
| Login attempt during network interruption | Application or browser handles the failure without crashing |
| Unicode and multi-byte characters in fields | Application handles input safely without layout or encoding issues |

---

## 🔹 Notes

Boundary Value Analysis is not applied to the Login form because the application does not provide clear minimum or maximum length requirements for the Username and Password fields.

Long input values are treated as destructive or edge case checks, not as boundary value tests.
