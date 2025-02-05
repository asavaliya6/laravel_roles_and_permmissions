## ACL - Roles and Permissions

- Create fresh laravel application starting from scratch ```composer create-project laravel/laravel example-app```

<h3>Install spatie/laravel-permission Package</h3>

```
composer require spatie/laravel-permission
```

- Also customize changes on the Spatie package, and get the config file in config/permission.php and migration files : 

```
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
php artisan migrate
```

- Create Product Migration :

```
php artisan make:migration create_products_table
php artisan migrate
```

- Update User Models => app/Models/User.php

- Create Models ```php artisan make:model Product```

- Add Middleware on => bootstrap/app.php

<h3>Create Authentication</h3>

- install the laravel/ui package : ```composer require laravel/ui```
- generate auth scaffolding : ```php artisan ui bootstrap --auth```
- see the better layout of the login and register page :```npm install``` ```npm run build```

- Create Routes => routes/web.php
- Add Controllers :

```
php artisan make:controller UserController
php artisan make:controller ProductController
php artisan make:controller RoleController
```

<h3>Add Blade Files</h3>

- Theme Layout => app.blade.php
- Users Module => index.blade.php create.blade.php edit.blade.php show.blade.php
- Roles Module => index.blade.php create.blade.php edit.blade.php show.blade.php
- Product Module => index.blade.php create.blade.php edit.blade.php show.blade.php

<h3>Create Seeder For Permissions and AdminUser</h3>

- create a seeder for permissions :
    => role-list
    => role-create
    => role-edit
    => role-delete
    => product-list
    => product-create
    => product-edit
    => product-delete

- first create a seeder ```php artisan make:seeder PermissionTableSeeder```
- execute the PermissionTableSeeder seeder ```php artisan db:seed --class=PermissionTableSeeder```
- create a new seeder for creating an admin user ```php artisan make:seeder CreateAdminUserSeeder```
- run seeder ```php artisan db:seed --class=CreateAdminUserSeeder```
- run app ```php artisan serve``` ```http://localhost:8000```

```
Email: admin@gmail.com
Password: 123456
```
