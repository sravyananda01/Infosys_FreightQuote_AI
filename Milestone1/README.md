# Milestone 1 — User Authentication Module

**Infosys Springboard 7.0 — Intelligent Freight Quote Generation**

## What This Milestone Is
This milestone builds the authentication layer for the Freight Quote Generation system: a Login, Signup, and Forgot Password flow, running as a Streamlit app inside Google Colab and exposed publicly through ngrok.

## Features Built
- **Login** — Username/Email + Password. Issues a JWT session token on success. Shows a single generic error on failure (doesn't reveal whether the username or password was wrong).
- **Signup** — Username, Email, Password, Confirm Password, Security Question (chosen from a fixed list), Security Answer. Rejects duplicate usernames/emails.
- **Forgot Password** — two recovery routes:
  - *Security Question* — verify the stored answer, then set a new password.
  - *Email OTP* — a 6-digit one-time code is emailed via Gmail SMTP, expires in 5 minutes.
- **JWT session handling** — token issued only at login; Signup and password-reset both route back to Login for a fresh token.
- **Field validation** — all fields mandatory; email format checked; password requires 8+ characters, upper/lowercase, a number, and a special symbol.
- **User Dashboard** — welcome message with logout.
- **Admin Dashboard** — separate hardcoded admin login; lists all registered users (username/email only, no password data).

## Tech Stack
- Streamlit (UI)
- PyJWT (session tokens)
- bcrypt (password hashing)
- SQLite (user storage)
- smtplib / Gmail SMTP (OTP delivery)
- pyngrok (public URL tunnel)
- Google Colab (hosting/runtime)

## How to Run
1. Open `Milestone1_Auth_Module.ipynb` in Google Colab.
2. Add these secrets in the Colab Secrets tab (key icon, left sidebar), enabling notebook access for each:
   - `JWT_SECRET` — any long random string
   - `NGROK_AUTHTOKEN` — from your ngrok.com dashboard
   - `EMAIL_ADDRESS` — the Gmail address that sends OTPs
   - `EMAIL_PASSWORD` — a Gmail App Password (requires 2-Step Verification)
3. Run the cells top to bottom.
4. Open the printed ngrok URL in your browser.
5. Admin login: username `admin`, password `Admin@123` (hardcoded in code — change if required).

## Screenshots
_Add screenshots here and reference them, e.g.:_

- Login: `screenshots/login.png`
- Signup: `screenshots/signup.png`
- Forgot Password — Security Question: `screenshots/forgot_security_question.png`
- Forgot Password — OTP: `screenshots/forgot_otp.png`
- OTP Email received: `screenshots/otp_email.png`
- User Dashboard: `screenshots/user_dashboard.png`
- Admin Dashboard: `screenshots/admin_dashboard.png`
-
