# juice-shop-hw3

## OWASP Juice Shop HW3 - Secure Login Form

**Course:** CSCE 477/703 - Web Security | Texas A&M University | Spring 2026  
**Student:** Harshini Kondepudi (harshinik7)

---

## 📋 Overview

This project is **Part 2** of HW3 for the Web Security course. It involves building a secure HTML and JavaScript login form that mimics the OWASP Juice Shop login page, implementing both **client-side** and **server-side** validation to meet all assignment requirements.

---

## 🎯 Assignment Requirements (Part 2)

Create a basic HTML and JavaScript login form that includes:
- ✅ **Email and password input fields**
- ✅ **Client-side validation to prevent empty fields**
- ✅ **A JavaScript function that checks:**
  - If the email contains "@"
  - If the password is at least 8 characters long
- ✅ **Server-side validation** (simulated)
- ✅ **Well-commented code** explaining implementation

---

## 📂 Project Structure

```
juice-shop-hw3/
├── index.html       # Complete login form (HTML + CSS + JavaScript)
└── README.md        # This file - comprehensive documentation
```

---

## 🔑 Implementation Details (100 Words)

The login form is implemented using pure HTML, CSS, and JavaScript without external libraries. **Client-side validation** prevents form submission if the email field is empty or lacks the "@" symbol, or if the password is fewer than 8 characters. The `validateEmail()` and `validatePassword()` JavaScript functions enforce these rules, displaying real-time error messages. Form submission is blocked until all validations pass. **Server-side validation** is simulated via the `simulateServerValidation()` function, which would normally send credentials to a backend API endpoint (`POST /api/login`) where parameterized queries prevent SQL injection and bcrypt verifies password hashes. The form mimics Juice Shop's design with modern gradient styling.

---

## 💻 How the Form Works

### 1. HTML Structure
- Two input fields: `<input type="email">` and `<input type="password">`
- Error message spans (`<span class="error-message">`) below each field
- Submit button and success message container
- Validation requirements clearly displayed on the page

### 2. Client-Side Validation (JavaScript)

**Email Validation Function:**
```javascript
function validateEmail(email) {
  if (email.trim() === '') return 'Email is required';
  if (!email.includes('@')) return 'Email must contain "@" symbol';
  return ''; // Valid
}
```

**Password Validation Function:**
```javascript
function validatePassword(password) {
  if (password === '') return 'Password is required';
  if (password.length < 8) return 'Password must be at least 8 characters long';
  return ''; // Valid
}
```

**Form Submission:**
- `e.preventDefault()` stops default form behavior
- Both validation functions are called
- If any errors exist, form submission is blocked
- Success triggers simulated server-side validation

### 3. Server-Side Validation (Simulated)

The `simulateServerValidation()` function demonstrates what a real backend would do:
- **SQL Injection Prevention:** Use parameterized queries
- **Password Verification:** Compare bcrypt hash
- **Rate Limiting:** Prevent brute-force attacks
- **CSRF Protection:** Validate tokens

---

## 🚀 How to Use

### Option 1: Open Locally
1. Clone this repository:
   ```bash
   git clone https://github.com/harshinik7/juice-shop-hw3.git
   cd juice-shop-hw3
   ```
2. Open `index.html` in any modern web browser
3. No server or build tools required!

### Option 2: View on GitHub
- **GitHub Repository:** https://github.com/harshinik7/juice-shop-hw3
- **Direct File:** https://github.com/harshinik7/juice-shop-hw3/blob/main/index.html

---

## 🧪 Testing the Form

### Valid Test Case:
- **Email:** `user@example.com`
- **Password:** `password123` (8+ characters)
- **Result:** ✅ Form submits successfully, success message appears

### Invalid Test Cases:
1. **Empty email:** Error: "Email is required"
2. **Email without @:** `userexample.com` → Error: "Email must contain '@' symbol"
3. **Short password:** `pass12` → Error: "Password must be at least 8 characters long"
4. **Empty password:** Error: "Password is required"

---

## 🎨 Design Features

- **Juice Shop-inspired UI:** Clean white card with gradient background
- **Real-time validation:** Errors appear on field blur
- **Visual feedback:** Error messages in red, success in green
- **Responsive design:** Works on desktop and mobile
- **Accessibility:** Proper labels, ARIA attributes, semantic HTML

---

## 📖 Code Highlights

### Key JavaScript Features:
- ✅ `addEventListener('blur')` for real-time validation
- ✅ `addEventListener('focus')` to clear errors
- ✅ `addEventListener('submit')` to handle form submission
- ✅ `e.preventDefault()` to stop default browser behavior
- ✅ Clear, descriptive function names
- ✅ Detailed code comments explaining each step

### Security Considerations:
- Input validation on both client and server sides
- No passwords stored in plain text (bcrypt hashing recommended)
- CSRF token validation noted for production
- Rate limiting to prevent brute-force attacks
- SQL injection prevention via parameterized queries

---

## 📝 Assignment Compliance Checklist

- ✅ **Email and password input fields** → Implemented
- ✅ **Client-side validation to prevent empty fields** → Implemented
- ✅ **JavaScript function checking @ in email** → `validateEmail()` function
- ✅ **JavaScript function checking 8-char password** → `validatePassword()` function
- ✅ **Server-side validation** → Simulated in `simulateServerValidation()`
- ✅ **100-word implementation explanation** → Provided above
- ✅ **GitHub link in document** → https://github.com/harshinik7/juice-shop-hw3
- ✅ **Well-explained README.md** → This file

---

## 👩‍💻 Author

**Harshini Kondepudi**  
GitHub: [@harshinik7](https://github.com/harshinik7)  
Course: CSCE 477/703 - Web Security  
University: Texas A&M University  
Semester: Spring 2026

---

## 📄 License

This project is for educational purposes as part of CSCE 477/703 coursework.

---

## 🙏 Acknowledgments

- **OWASP Juice Shop** for providing an intentionally vulnerable application for learning
- **CSCE 477/703 Teaching Team** for comprehensive web security education
