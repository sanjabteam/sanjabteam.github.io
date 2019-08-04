# Install sanjab

## Requirements
* PHP 7.1.3+
* Laravel 5.8.*
* Composer
* NPM and laravel mix (optional)

## Install using composer


1. Open your laravel project directory in terminal.

2. Use composer command to install sanjab on your project.
```bash
composer require sanjabteam/sanjab
```

3. Install sanjab using following command.
```bash
php artisan sanjab:install
```
> Checkout Sanjab\Models\SanjabUser trait added to User model.
```php
use Sanjab\Models\SanjabUser;

class User extends Authenticatable
{
    use Notifiable, SanjabUser;
```

4. Migrate database.
```bash
php artisan migrate
```

5. Create new user.
```bash
php artisan tinker
Psy Shell v0.9.9 (PHP 7.2.12 — cli) by Justin Hileman
>>> User::create(['email' => 'test@test.com', 'name' => 'sanjab', 'password' => bcrypt("123456")])
```

6. Use following command to convert created user to sanjab super admin.
```bash
php artisan sanjab:make:admin --user=test@test.com
```
> --user is user email. if you want to use something else as username input you need to change config in config/sanjab.php

```php 'login' => [...]```

7. Open `yourwebsite/admin` to login to admin panel.

8. Congratulations! you installed sanjab admin panel successfully.😊

