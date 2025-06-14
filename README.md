# 📝 User Registration Form – HTML + JS + Django Backend

This project provides a **user registration page** that collects user details and posts them to a Django backend. It includes real-time password confirmation validation, file upload support, and responsive form handling.

---

## 🔧 Features

- Clean and responsive HTML form.
- Real-time validation for matching passwords.
- Profile picture upload with preview option.
- Dropdown user type selector (Patient/Doctor).
- Form submission using `FormData` to Django backend endpoint.
- JavaScript-based error handling and alerts.

---

## 📄 Form Fields

| Field              | Type        | Required | Notes                          |
|-------------------|-------------|----------|--------------------------------|
| First Name        | Text        | ✅       |                                |
| Last Name         | Text        | ✅       |                                |
| Username          | Text        | ✅       | Must be unique                 |
| Email             | Email       | ✅       | Must be a valid email address |
| Password          | Password    | ✅       | Minimum 8 characters suggested |
| Confirm Password  | Password    | ✅       | Must match `Password`          |
| User Type         | Select Box  | ✅       | Options: Patient, Doctor       |
| Profile Picture   | File (Image)| Optional | PNG/JPG only                   |
| Address Line 1    | Text        | ✅       |                                |
| City              | Text        | ✅       |                                |
| State             | Text        | ✅       |                                |
| Pincode           | Text        | ✅       | 6-digit Indian postal code     |

---

## 🚀 How It Works

1. User fills out the form.
2. JavaScript checks if passwords match in real-time.
3. On submit, the form data is collected using `FormData()`.
4. A POST request is made to `http://127.0.0.1:8000/api/register/`.
5. If successful → redirects to login page. Otherwise → shows an alert.
✅ If successful:
→ User is redirected to the Login page.

On the login page, the user enters their username and password.

A POST request is made to:
http://127.0.0.1:8000/api/token/ to obtain access and refresh tokens.

✅ If login is successful:
→ Tokens are stored in localStorage.
→ User is redirected to the Dashboard.

The Dashboard fetches the user's profile data from:
http://127.0.0.1:8000/api/dashboard/ using the access token.

🔒 Logout button clears the access/refresh tokens and redirects to login.

---

## 📁 Files

- `register.html` — Main HTML form
- `style.css` — Optional external CSS (linked in `<head>`)
- Backend Django API endpoint: `/api/register/` (expects POST FormData)

---

## 📦 Requirements (Backend)

- Django with REST framework
- Simple JWT or similar auth system (optional)
- Media configuration for file uploads

---

## 📸 Screenshot

![Register Page Demo](screenshot.png)

---


## 📄 License

MIT License
## 🛠️ Setup Instructions

Follow the steps below to run this project locally:

### 1. Clone the repository

```bash
git clone https://github.com/AMANKUMAR22MCA/django-user-registration-system.git
cd django-user-registration-system
```

### 2. Create and activate a virtual environment

```bash
# Create virtual environment
python -m venv venv

# Activate it
# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Apply migrations for the `accounts` app

```bash
python manage.py makemigrations accounts
python manage.py migrate accounts
python manage.py migrate 
```

### 5. Run the development server

```bash
python manage.py runserver
```

### 6. Access the frontend

Open your browser and navigate to:

```
http://127.0.0.1:5500/frontend/index.html
```

Ensure that `register.html`, `index.html`, and other static files are served correctly by placing them in the appropriate static directory or hosting them via a lightweight frontend server.
