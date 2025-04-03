# 🩸 Blood Bank Website

A modern, responsive, and professional blood donation management system that connects blood donors with hospitals in need.

![Blood Bank Website](https://img.shields.io/badge/Blood%20Bank-Website-red)
![PHP](https://img.shields.io/badge/PHP-7.4+-blue)
![MySQL](https://img.shields.io/badge/MySQL-5.7+-orange)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-purple)
![Font Awesome](https://img.shields.io/badge/Font%20Awesome-6.0-lightgrey)

## 📋 Table of Contents

- [Features](#features)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [Database Setup](#database-setup)
- [Project Structure](#project-structure)
- [Key Components](#key-components)
- [User Interface](#user-interface)
- [Email Notifications](#email-notifications)
- [Security Considerations](#security-considerations)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

- **Modern UI/UX**: Sleek, responsive design with smooth animations and transitions
- **Donor Registration**: Easy registration process for blood donors
- **Donor Search**: Hospitals can search for donors by blood group and city
- **Real-time Notifications**: Email notifications for blood requests
- **Hospital Verification**: Secure hospital login system
- **Responsive Design**: Works seamlessly on all devices (desktop, tablet, mobile)
- **Interactive Elements**: Engaging UI elements with hover effects and animations
- **Blood Type Visualization**: Visual representation of different blood types
- **Statistics Dashboard**: Display of key metrics and statistics

## 🛠️ Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5.3, Font Awesome 6.0
- **Backend**: PHP 7.4+
- **Database**: MySQL 5.7+
- **Email**: PHPMailer for sending notifications
- **Fonts**: Google Fonts (Poppins)
- **Icons**: Font Awesome

## 🚀 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/blood_bank_website.git
   ```

2. Navigate to the project directory:
   ```bash
   cd blood_bank_website
   ```

3. Set up a local web server (XAMPP, WAMP, or MAMP)

4. Place the project files in your web server's document root (e.g., `htdocs` for XAMPP)

5. Import the database schema (see [Database Setup](#database-setup))

6. Configure the database connection in `config/db.php`

7. Configure email settings in `send_request.php` (see [Email Notifications](#email-notifications))

8. Access the website through your web browser:
   ```
   http://localhost/blood_bank_website
   ```

## 💾 Database Setup

1. Create a new MySQL database named `blood_bank`

2. Import the database schema from `database.sql`:
   ```sql
   CREATE DATABASE blood_bank;
   USE blood_bank;

   CREATE TABLE donors (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(100),
       age INT,
       phone VARCHAR(15),
       email VARCHAR(100),
       blood_group VARCHAR(10),
       city VARCHAR(100),
       address TEXT
   );
   ```

3. Create a table for hospitals (if not included in the schema):
   ```sql
   CREATE TABLE hospitals (
       id INT AUTO_INCREMENT PRIMARY KEY,
       hospital_name VARCHAR(100),
       username VARCHAR(50),
       password VARCHAR(255)
   );
   ```

## 📁 Project Structure

```
blood_bank_website/
├── config/
│   └── db.php                 # Database configuration
├── css/
│   └── style.css              # Custom CSS styles
├── js/
│   └── script.js              # JavaScript functionality
├── vendor/                    # Composer dependencies
├── donor.php                  # Donor registration page
├── receiver.php               # Donor search page
├── search_donors.php          # Donor search functionality
├── send_request.php           # Email notification system
├── verify_hospital.php        # Hospital verification
├── header.php                 # Common header template
├── index.php                  # Landing page
├── database.sql               # Database schema
├── composer.json              # Composer configuration
└── composer.lock              # Composer lock file
```

## 🔑 Key Components

### Donor Registration (`donor.php`)
- Form for collecting donor information
- Input validation
- Database insertion
- Display of registered donors

### Donor Search (`receiver.php`)
- Search form for hospitals
- Real-time search results
- Hospital login modal
- Request sending functionality

### Email Notifications (`send_request.php`)
- PHPMailer integration
- SMTP configuration
- Email template for blood requests

### Hospital Verification (`verify_hospital.php`)
- Secure hospital authentication
- Database verification
- Session management

## 🎨 User Interface

The website features a modern, responsive design with the following UI components:

### Landing Page
- Hero section with call-to-action buttons
- Features section highlighting key benefits
- Blood types visualization with interactive circles
- Statistics dashboard
- Call-to-action section

### Donor Registration
- Clean form layout with proper validation
- Responsive table for donor list
- Visual feedback for form submission

### Donor Search
- Intuitive search interface
- Loading animations
- Modern table layout for results
- Bootstrap modal for hospital login
- Success/error notifications

## 📧 Email Notifications

The system uses PHPMailer to send email notifications:

1. Configure SMTP settings in `send_request.php`:
   ```php
   $mail->isSMTP();
   $mail->Host = 'smtp.gmail.com';
   $mail->SMTPAuth = true;
   $mail->Username = 'your-email@gmail.com';
   $mail->Password = 'your-app-password';
   $mail->SMTPSecure = PHPMailer::ENCRYPTION_STARTTLS;
   $mail->Port = 587;
   ```

2. Customize email content:
   ```php
   $mail->setFrom('your-email@gmail.com', 'Blood Bank');
   $mail->addAddress($email);
   $mail->Subject = 'Blood Donation Request';
   $mail->Body = "Hello, a hospital ($hospital) is requesting your blood donation. Please contact them.";
   ```

## 🔒 Security Considerations

- **SQL Injection Prevention**: Prepared statements for database queries
- **Input Validation**: Client-side and server-side validation
- **Password Security**: Secure storage of hospital credentials
- **Email Security**: SMTP authentication for email notifications
- **XSS Prevention**: Proper escaping of user input

## 🚀 Future Enhancements

- User authentication for donors
- Donor profile management
- Blood donation history tracking
- Hospital dashboard
- Admin panel for system management
- Mobile app integration
- SMS notifications
- Blood availability status
- Donation appointment scheduling

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

<p align="center">Made with ❤️ for saving lives through blood donation</p> 