# Hospital Management System

A comprehensive web-based hospital management system that connects blood donors with receivers, featuring separate dashboards for donors, receivers, and administrators.

## Features

### 🩸 For Blood Donors
- **Easy Registration**: Simple signup process with blood group verification
- **Donation Tracking**: Record and track all blood donations
- **Smart Matching**: Get notified about compatible blood requests
- **Donation History**: View complete donation history with status updates
- **Profile Management**: Update personal and medical information

### 🏥 For Blood Receivers
- **Blood Requests**: Submit urgent or scheduled blood requests
- **Donor Search**: Find compatible donors in your area
- **Request Tracking**: Monitor the status of your blood requests
- **Emergency Support**: Priority handling for critical requests
- **Compatibility Guide**: Blood group compatibility information

### 👨‍💼 For Administrators
- **User Management**: Manage all registered donors and receivers
- **Dashboard Analytics**: View system statistics and trends
- **Request Monitoring**: Oversee all blood requests and donations
- **System Control**: Activate/deactivate users and manage the platform

## Technology Stack

- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5
- **Backend**: PHP 7.4+
- **Database**: MySQL 5.7+
- **Authentication**: Session-based with password hashing
- **Security**: Input sanitization, SQL injection prevention

## Installation

### Prerequisites

- PHP 7.4 or higher
- MySQL 5.7 or higher
- Apache/Nginx web server
- phpMyAdmin (optional, for database management)

### Step 1: Download and Setup

1. Download or clone the project files
2. Extract to your web server directory (e.g., `htdocs`, `www`, or `public_html`)

bash
# If using Git
git clone <repository-url> hospital_management_system
cd hospital_management_system

### Step 2: Database Setup

1. Create a new MySQL database:
sql
CREATE DATABASE hospital_management;
2. Import the database schema:
bash
mysql -u your_username -p hospital_management < database/hospital_db.sql


Or use phpMyAdmin:
- Open phpMyAdmin
- Create a new database named `hospital_management`
- Import the `database/hospital_db.sql` file

### Step 3: Configuration

1. Update database configuration in `includes/config.php`:
php
define('DB_HOST', 'localhost');
define('DB_USER', 'your_username');
define('DB_PASS', 'your_password');
define('DB_NAME', 'hospital_management');


2. Update the base URL if needed:
php
define('BASE_URL', 'http://localhost/hospital_management_system/');

### Step 4: File Permissions

Ensure proper file permissions:
```bash
chmod 755 hospital_management_system/
chmod 644 hospital_management_system/*.php
chmod 644 hospital_management_system/includes/*.php
```

### Step 5: Access the Application

1. Open your web browser
2. Navigate to: `http://localhost/hospital_management_system/`
3. The application should load successfully

 Default Login Credentials

 Administrator
- **Username**: `admin`
- **Password**: `password`
- **Access**: `http://localhost/hospital_management_system/admin/login.php`

 Test Users
You can register new users through the registration page or create test accounts manually.

Project Structure
hospital_management_system/
├── admin/                  # Admin panel files
│   ├── dashboard.php      # Admin dashboard
│   ├── login.php          # Admin login
│   ├── users.php          # User management
│   └── logout.php         # Admin logout
├── donor/                 # Donor-specific files
│   ├── dashboard.php      # Donor dashboard
│   ├── add_donation.php   # Add donation form
│   ├── profile.php        # Donor profile management
│   └── donations.php      # Donation history
├── receiver/              # Receiver-specific files
│   ├── dashboard.php      # Receiver dashboard
│   ├── add_request.php    # Blood request form
│   ├── profile.php        # Receiver profile management
│   └── requests.php       # Request history
├── includes/              # Common PHP includes
│   ├── config.php         # Database and app configuration
│   ├── header.php         # Common header
│   └── footer.php         # Common footer
├── css/                   # Stylesheets
│   └── style.css          # Main stylesheet
├── js/                    # JavaScript files
│   └── script.js          # Main JavaScript
├── images/                # Image assets
├── database/              # Database files
│   └── hospital_db.sql    # Database schema
├── index.php              # Homepage
├── login.php              # User login
├── register.php           # User registration
├── logout.php             # User logout
├── about.php              # About page
├── contact.php            # Contact page
└── README.md              # This file
```

## Database Schema

### Tables

1. **admin** - Administrator accounts
2. **users** - Donor and receiver accounts
3. **donations** - Blood donation records
4. **blood_requests** - Blood request records
5. **blood_inventory** - Blood stock management
6. **contact_messages** - Contact form submissions

### Key Relationships

- Users can be either donors or receivers
- Donations are linked to donor users
- Blood requests are linked to receiver users
- Blood inventory tracks available blood by group

## Usage Guide

### For Donors

1. **Registration**: Register with your details and select "Blood Donor"
2. **Login**: Access your donor dashboard
3. **Add Donations**: Record your blood donations with hospital details
4. **View Requests**: See matching blood requests from receivers
5. **Track Impact**: Monitor your donation history and impact

### For Receivers

1. **Registration**: Register with your details and select "Blood Receiver"
2. **Login**: Access your receiver dashboard
3. **Submit Requests**: Create blood requests with urgency levels
4. **Find Donors**: Search for compatible donors
5. **Track Requests**: Monitor the status of your requests

### For Administrators

1. **Login**: Use admin credentials to access admin panel
2. **User Management**: View, activate, or deactivate users
3. **Monitor System**: Track donations, requests, and system usage
4. **Generate Reports**: View analytics and system statistics

## Security Features

- **Password Hashing**: All passwords are securely hashed
- **Input Sanitization**: All user inputs are sanitized
- **SQL Injection Prevention**: Prepared statements used throughout
- **Session Management**: Secure session handling
- **Access Control**: Role-based access restrictions

## Customization

### Styling
- Modify `css/style.css` for custom styling
- Bootstrap 5 classes can be used throughout
- Color scheme can be updated in CSS variables

### Functionality
- Add new features by creating additional PHP files
- Extend database schema as needed
- Integrate with external APIs for enhanced functionality

## Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Check database credentials in `includes/config.php`
   - Ensure MySQL service is running
   - Verify database exists and is accessible

2. **Page Not Found (404)**
   - Check file permissions
   - Verify web server configuration
   - Ensure all files are uploaded correctly

3. **Login Issues**
   - Clear browser cache and cookies
   - Check database for user records
   - Verify password hashing is working

4. **Styling Issues**
   - Check if CSS files are loading
   - Verify Bootstrap CDN links
   - Clear browser cache

### Error Logging

Enable PHP error logging for debugging:
```php
ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the [MIT License](LICENSE).

## Support

For support and questions:
- Email: support@hospitalmanagement.com
- Phone: +1 (555) 123-4567
- Emergency: +1 (555) 911-BLOOD

## Changelog

### Version 1.0.0
- Initial release
- Basic donor/receiver functionality
- Admin panel
- User authentication
- Blood request/donation system

## Future Enhancements
- Mobile app development
- SMS/Email notifications
- GPS-based donor matching
- Blood bank inventory integration
- Advanced reporting and analytics
- Multi-language support
**Note**: This system is designed for educational and demonstration purposes. For production use, additional security measures, testing, and compliance with healthcare regulations may be required.

