## 🍀 Clover PHP

Clover PHP is a modern, unopinionated, and lightweight Express.js-style framework for PHP 8.4.
It helps you build REST APIs, web apps, and microservices with the simplicity of Express.js and the power of modern PHP.

[![Tests](https://github.com/cloverphp/clover/actions/workflows/tests.yml/badge.svg)](https://github.com/cloverphp/clover/actions/workflows/tests.yml)
![Packagist Version](https://img.shields.io/packagist/v/cloverphp/clover?style=flat&logo=composer&logoColor=%23fff)
![Packagist Dependency Version](https://img.shields.io/packagist/dependency-v/cloverphp/clover/php?style=flat&logo=php&logoColor=blue&label=PHP&color=blue)
![Packagist License](https://img.shields.io/packagist/l/cloverphp/clover?style=flat&label=License&color=blue)
![Packagist Downloads](https://img.shields.io/packagist/dt/cloverphp/clover?style=flat&logo=packagist&label=Downloads&color=blue)
![Packagist Stars](https://img.shields.io/packagist/stars/cloverphp/clover?style=flat&logo=github&logoColor=%23ffffff&label=%F0%9F%8C%9F%20Stars)


---

## ✨ Features

🚀 Minimal & Fast – Simple API design, inspired by Express.js.

⚡ Async Support – Built with PHP Fibers & AMPHP for non-blocking I/O.

🗂️ Routing System – Intuitive get(), post(), etc., with async router support.

🔑 Auth Ready – Supports sessions, cookies, and JWT-based authentication.

🧩 Extensible Middleware – Add global and route-level middleware for logging, security, and validation.

💾 Database Agnostic – Works with both SQL and NoSQL databases.(Upcoming)

🛠️ MVC Support – Controllers, models, and views with interfaces for clean architecture.

🛡️ Error Handling & Logging – Developer-friendly error responses and logging tools.

🎨 Unopinionated – Flexible enough for small apps or large enterprise projects.

📦 Composer & PSR-12 – Modern PHP practices with full Composer/PSR-12 compliance.



---

## 📦 Installation

```bash
composer create-project cloverphp/clover my-app
```

```bash
cd my-app
```

```bash
php -S localhost:3000 -t public
```

---

## 🚀 Quick Start

```php
<?php

require_once __DIR__ . "/vendor/autoload.php";

use Clover\Application;
use Clover\Request;
use Clover\Response;
use Clover\Router;

$app = new Application();
$router = new Router();

$app->use($router);

// Home route
$router->get("/", fn(Request $req, Response $res) =>
    $res->send("Welcome to 🍀 Clover PHP!")
);

// Example POST route
$router->post("/posts", fn(Request $req, Response $res) => {
    $data = $req->json();
    $res->json([
        "message" => "Post created successfully",
        "data" => $data
    ]);
});

// Start server
$app::run(3000, "Clover PHP running on http://localhost:3000");
```

---

## 📂 Project Structure

```bash
my-app/
├── app/
│   ├── Controllers/
│   ├── Models/
│   └── Views/
├── public/
│   └── index.php
├── vendor/
├── composer.json
└── README.md
```

---

## 🔑 Example Middleware

```php
$app->use(function (Request $req, Response $res, callable $next) {
    $res->setHeader("X-Powered-By", "Clover PHP");
    $next($req, $res);
});
```

---

## 🛡️ License

Clover PHP is open-sourced software licensed under the ![Packagist License](https://img.shields.io/packagist/l/cloverphp/clover?style=flat&label=License&color=blue)

---

