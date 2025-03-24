# Website Setup Guide

## Prerequisites
1. Install XAMPP (includes Apache, MySQL, and PHP)
   - Download from: https://www.apachefriends.org/
   - Choose the latest version for Windows
   - During installation, at minimum select:
     - Apache
     - PHP
     - MySQL (optional, if you plan to use a database)

2. Install Git
   - Download from: https://git-scm.com/download/win
   - Use default installation options

## Setup Steps

### 1. Configure XAMPP
1. Open XAMPP Control Panel
2. Start Apache service
3. Click "Config" next to Apache
4. Select "httpd.conf"
5. Find and modify these lines:
   ```apache
   DocumentRoot "C:/xampp/htdocs"
   <Directory "C:/xampp/htdocs">
   ```
   Change to:
   ```apache
   DocumentRoot "C:/xampp/htdocs/php_website"
   <Directory "C:/xampp/htdocs/php_website">
   ```

### 2. Clone the Repository
1. Open Command Prompt
2. Navigate to XAMPP's htdocs folder:
   ```bash
   cd C:\xampp\htdocs
   ```
3. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/unm_prep_01_private.git php_website
   ```

### 3. File Permissions
1. Right-click on the `php_website` folder
2. Select "Properties"
3. Go to "Security" tab
4. Click "Edit"
5. Add "Everyone" if not present
6. Set permissions:
   - Read & Execute
   - List folder contents
   - Read
   - Write (for specific folders that need it)

### 4. Configure PHP
1. Open XAMPP Control Panel
2. Click "Config" next to Apache
3. Select "PHP (php.ini)"
4. Find and modify these settings:
   ```ini
   display_errors = On
   error_reporting = E_ALL
   ```
5. Save and close

### 5. Test the Setup
1. Open your web browser
2. Visit: http://localhost:8000
3. You should see the website homepage

## Troubleshooting

### Common Issues

1. **Apache won't start**
   - Check if port 80 is in use
   - Open Command Prompt as Administrator
   - Run: `netstat -ano | findstr :80`
   - If port is in use, change Apache port in XAMPP Control Panel

2. **404 Errors**
   - Verify file paths in `httpd.conf`
   - Check file permissions
   - Ensure all files are in correct locations

3. **PHP errors not showing**
   - Verify PHP error settings in `php.ini`
   - Check Apache error logs in XAMPP Control Panel

### Log Files
- Apache logs: `C:\xampp\apache\logs\error.log`
- PHP logs: `C:\xampp\php\logs\php_error_log`

## Development Workflow

1. **Making Changes**
   ```bash
   cd C:\xampp\htdocs\php_website
   git pull  # Get latest changes
   # Make your changes
   git add .
   git commit -m "Your commit message"
   git push
   ```

2. **Testing Changes**
   - Always test on localhost first
   - Check all pages and functionality
   - Verify responsive design

3. **Deployment**
   - Changes pushed to main branch will be automatically deployed
   - Verify deployment at: https://artsmetrics.net/projects/unmprep/

## Additional Notes

1. **File Structure**
   ```
   php_website/
   ├── css/
   ├── js/
   ├── includes/
   ├── prompts/
   └── index.php
   ```

2. **Important Files**
   - `index.php`: Main entry point
   - `includes/header.php`: Common header
   - `includes/footer.php`: Common footer
   - `css/style.css`: Main stylesheet
   - `js/main.js`: Main JavaScript file

3. **Backup**
   - Regular backups are stored in the Git repository
   - Additional backups can be created using:
     ```bash
     git bundle create backup.bundle HEAD main
     ```

## Support
For additional support or questions, please contact the development team or create an issue in the repository. 