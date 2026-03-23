# juice-shop-hw3

## OWASP Juice Shop HW3 - Secure Login Form


## Overview

This project is part of HW3 for the Web Security course. It involves:
1. Analyzing vulnerabilities in OWASP Juice Shop
2. Building a secure HTML/JavaScript login form
3. Attempting exploitation of the form to test its defenses

---

## Project Structure

```
juice-shop-hw3/
|-- index.html       # Secure login form with client-side + simulated server-side validation
|-- README.md        # Project documentation
```

---

## Features of the Login Form (index.html)

- **Email & Password input fields** styled to mimic Juice Shop's UI
- **Client-side validation:**
  - Email field must be non-empty and contain `@`
  - Password must be at least 8 characters long
  - Real-time validation feedback on field blur
- **XSS Prevention:** A `sanitize()` function encodes HTML entities before any user input is used in the DOM, preventing reflected XSS attacks
- **Empty field prevention:** Form submission is blocked if either field is empty or invalid
- **Server-side simulation:** On valid submission, the form simulates a `POST /api/login` call (with notes for CSRF tokens, rate limiting, and bcrypt password comparison in a real backend)

---

## Security Measures Implemented

| Threat | Mitigation Used |
|---|---|
| XSS (Cross-Site Scripting) | HTML entity encoding via `sanitize()` function |
| Empty field injection | Client-side required field validation |
| Weak password | Minimum 8-character password enforcement |
| SQL Injection (server-side) | Parameterized queries recommended in comments |
| Brute Force | Rate limiting noted in server-side simulation |

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/harshinik7/juice-shop-hw3.git
   ```
2. Open `index.html` in any modern web browser — no server required for the frontend demo.

---

## Live Demo

You can view the form by opening `index.html` directly in a browser or via GitHub Pages (if enabled).

---

## Author

**harshinik7** | Texas A&M University
