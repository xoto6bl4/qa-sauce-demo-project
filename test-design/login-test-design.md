# Login Test Design – Sauce Demo

## 🎯 Feature: Login form

### Input fields:
- Username
- Password

---

## 🔹 Equivalence Partitioning

### Username
**Valid equivalence class:**
- Existing and correct username

**Invalid equivalence classes:**
- Non-existing username
- Empty username
- Username with special characters

### Password
**Valid equivalence class:**
- Correct password

**Invalid equivalence classes:**
- Incorrect password
- Empty password
- Password with less than minimum required length

---

## 🔹 Boundary Value Analysis

### Username field
| Case | Value | Expected Result |
|-----|------|----------------|
| Lower boundary | 1 character | Error message |
| Upper boundary | Max allowed length | Successful input |
| Below lower boundary | Empty value | Error message |
| Above upper boundary | Exceeds max length | Error message |

### Password field
| Case | Value | Expected Result |
|-----|------|----------------|
| Lower boundary | 1 character | Error message |
| Upper boundary | Max allowed length | Successful input |
| Below lower boundary | Empty value | Error message |
| Above upper boundary | Exceeds max length | Error message |
