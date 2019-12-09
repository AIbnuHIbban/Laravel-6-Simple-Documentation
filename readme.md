# Simple Documentation for Laravel 6

Dibuat untuk mempermudah yang baru saja terjun ke Laravel 6

# Cara Install

## Menggunakan Composer
```php
composer create-project --prefer-dist laravel/laravel blog
```

## Menggunakan Git Repo Saya

 - **Setup Installer with ADMIN LTE 3 Dashboard**
```php
git clone https://github.com/AIbnuHIbban/Laravel-6-Setup-AdminLT3.git nama_project
```
 - **Setup Installer with CORE UI Dashboard**
```php
git clone https://github.com/AIbnuHIbban/Laravel-6-Setup-CoreUI.git nama_project
```
 - **Setup Installer with Azzara Dashboard**
```php
git clone https://github.com/AIbnuHIbban/Laravel-6-Setup-Azzara-Template.git nama_project
```
 - **Setup Installer with Stisla Dashboard**
```php
git clone https://github.com/AIbnuHIbban/Laravel-6-Setup-Stisla.git nama_project
```
## Membuat Authentication

Install Laravel UI
```php
composer require laravel/ui --dev
```

Lalu,

 - Jika ingin menggunakan VueJS
 ```php
php artisan ui vue --auth
```
 - Jika ingin menggunakan ReactJS
 ```php
php artisan ui react --auth
``` 
 - Jika ingin menggunakan Bootstrap (Jquery)
  ```php
php artisan ui bootstrap --auth
```

## Memanggil Data User Auth
```php
Auth::user();
```
```php
Auth::user()->id;
```
## Mengecek jika User Auth sedang Login
```php
use Illuminate\Support\Facades\Auth;

if (Auth::check()) {
    // Jika user sedang login maka...
}
```
## Logout User Auth
```php
Auth::logout();
```
## "Ingat Saya" User Auth
```php
if (Auth::attempt(['email' => $email, 'password' => $password], $remember)) {
    // Jika User mengklik ingat saya...
}
```

## Login menggunakan ID User Auth
```php
Auth::loginUsingId(1);

// Jika Ingat Saya / Remember me di klik 
Auth::loginUsingId(1, true);
```



## Contoh Seeder
```php
		DB::table('users')->insert([
            'name' => Str::random(10),
            'email' => Str::random(10).'@gmail.com',
            'password' => bcrypt('secret'),
        ]);
```
## Mendapatkan URI 
```
Request::segment(1) 
Request::segment(2) 
```

## Pencarian Data di Database
```php
->where('name', 'like', 'T%')
```

## Artisan tanpa menulis di terminal
Jika anda lambat dalam menulis, ada alternatif lain yang juga bisa digunakan pada anda yang cepat dalam menulis namun tidak ingin menghafal perintah yang harus di tulis, berikut langkah-langkahnya :

> **Hanya untuk pengguna Visual Studio Code dan Perintah di Ekstensi ini Tidak Komplit (Sebagian besar perintah untuk membuat-membuat saja)**

 1. Pastikan anda menginstall Visual Studio Code
 2. Install Ekstensi "**Laravel Artisan**"
 3. Jika Installasi sudah selesai, Tekan Tombol CTRL + P, maka anda bisa memilih perintah apa yang ingin anda lakukan. 
Contoh ingin membuat controller, anda tinggal tekan CTRL + P lalu tekan **contr** nanti akan langsung muncul suggest untuk **Make:Controller**, tekan saja Enter untuk melanjutkan step berikutnya.
Dengan cara ini anda juga bisa membuat Models, Seeder, Migration, dan lainnya..


