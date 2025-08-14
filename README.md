# Quizard — Online Examination System (PHP + MySQL)

**Live Demo:** https://quizard.wuaze.com/index.php

---

## Overview

**Quizard** is a full-featured, web-based MCQ (Multiple Choice Questions) exam system developed in PHP with MySQL backend. It supports both **user** and **admin** interfaces:

- **User Side**:  
  - Registration & Login  
  - Profile management  
  - Take exams (MCQ format)  
  - View exam results and answers

- **Admin Panel**:
  - Login-protected dashboard  
  - Manage users (enable/disable/delete)  
  - Add, edit, or remove questions  
  - View exam stats and control the test flow

---

## Project Structure

OnlineExamination-PHP/

├── index.php, register.php, exam.php, profile.php, final.php, viewans.php, starttest.php
 
├── vendor/ (external libraries)
 
├── css/, js/, img/
 
├── lib/ (Database, Session classes + .htaccess)
 
├── classes/ (User.php, Exam.php, Admin.php, Process.php)
 
├── helpers/ (Format.php + .htaccess)
 
├── config/ (config.php + .htaccess)
 
└── inc/ (header.php, footer.php)
 
└── admin/ (admin index, login, users, quesadd, queslist + their inc/css)



---

## Deployment (on InfinityFree)

1. **Create a Free Project Hosting Account**  
   Choose a subdomain like `quizard.wuaze.com`.

2. **Upload Project Files**  
   Upload your project folder into `htdocs/`.

3. **Database Setup**  
   - Create a MySQL database via cPanel.  
   - Import your `.sql` schema.  
   - Update `config/config.php` and `lib/Database.php` with your DB credentials (host, user, pass, name).

4. **Enable SSL & Force HTTPS**  
   - In InfinityFree, add the free SSL certificate with CNAME validation.  
   - After activation, add a rewrite rule in `htdocs/.htaccess` to force HTTPS.

5. **Fix Relative Paths (Admin Panel)**  
   Update `inc/header.php` and `inc/footer.php` to use **absolute asset URLs** like `/css/`, `/vendor/...` so the theme loads properly in both root and `/admin/`.

6. **Security & Permissions**  
   - Set permissions: Folders = 755, Files = 644  
   - Deny public access to `config/`, `classes/`, `lib/`, `helpers/` with `.htaccess`  
   - Turn off PHP error display in production  
   - Remove `01 LOGIN DETAILS & PROJECT INFO.txt` files

7. **Optional: Email Functionality**  
   InfinityFree restricts PHP `mail()`. Use SMTP (with PHPMailer) or an API-based email service (e.g., SendGrid, Mailgun, Brevo).

---

## How to Use

### User Flow
1. Visit `/register.php` to create a user account  
2. Login via `/index.php`  
3. Take exams on `/exam.php` via `starttest.php`, finish on `final.php`, and use `viewans.php` to review answers

### Admin Flow
1. Visit `/admin/login.php` and login with your admin credentials  
2. Manage users (`users.php`), add questions (`quesadd.php`), or view existing ones (`queslist.php`) from the dashboard

---

## Security & Future Enhancements

- **Passwords** are currently stored using MD5 — consider upgrading to `password_hash()`  
- **Sensitive files** are protected with `.htaccess`  
- Consider enabling **session timeout** and **CSRF protection**
- Email password reset and OTP features could be improved with an external mail service

---

## License

MIT License — feel free to use and modify.

---

### Contact / Help

Need help with setup or customization? Feel free to reach out by number i profile —I’ll help make Quizard work perfectly for your needs.



