# Wiki Installation Guide


## Installation Steps
This project uses the `release` branch of the [BookStack GitHub repository](https://github.com/BookStackApp/BookStack) as a stable channel for updates. Installation may be somewhat complex but will be simplified in future releases. Some experience with PHP or Laravel will be beneficial.

### 1. Clone the Repository
Clone the `release` branch of the BookStack repository into a folder:
```sh
git clone https://github.com/RizkyMardiyansyah/wiki.git wiki
```

### 2. Navigate to the Application Folder
```sh
cd wiki
```

### 3. Install Dependencies
Run the following command to install PHP dependencies:
```sh
composer install --no-dev
```

### 4. Configure Environment
Copy the `.env.example` file to `.env` and update it with your own database and mail settings:
```sh
cp .env.example .env
```
Edit the `.env` file with your preferred database and mail configuration.

### 5. Set Permissions
Ensure the following folders are writable by the web server:
- `storage`
- `bootstrap/cache`
- `public/uploads`

For more details, refer to [this guide](https://bookstackapp.com/docs/admin/installation/#file-permissions).

### 6. Generate Application Key
Run the following command to generate a unique application key:
```sh
php artisan key:generate
```

### 7. Configure URL Rewrites
If not using Apache or if `.htaccess` files are disabled, you must create URL rewrite rules. See the [official documentation](https://bookstackapp.com/docs/admin/installation/#url-rewrites) for details.

### 8. Set Web Root
Ensure your web server points to the `public` folder:
- **Nginx**: Use the `root` setting.
- **Apache**: Use the `DocumentRoot` setting.

### 9. Run Database Migrations
```sh
php artisan migrate
```

### 10. Installation Complete!
You can now log in using the default credentials:
- **Email**: `admin@admin.com`
- **Password**: `password`

⚠ **Important:** Change the default admin credentials immediately after your first login.
