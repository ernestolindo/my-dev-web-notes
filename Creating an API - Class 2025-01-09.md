Creating `routes/api.php`
```powershell
php artisan install:api
```

We need routes to execute the code from outside. Route (method GET) to TaskController
```powershell
Route::get('tasks', [TaskController::class, 'index']);
```

