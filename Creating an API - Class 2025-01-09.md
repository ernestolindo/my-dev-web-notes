Creating `routes/api.php`
```powershell
php artisan install:api
```

We need routes to execute the code from outside. Route (method GET) to TaskController
```powershell
Route::get('tasks', [TaskController::class, 'index']);
```

In PostMan API we send:
```powershell
http://127.0.0.1:8000/api/tasks
```

The response is all the *tasks* models from the database:
```powershell
{
    "data": []
}
```

Creating a new task:
