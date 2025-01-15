`sanctum` is going to authenticate the user with a [[Token-based authentication system]]
Laravel Sanctum is **an authentication system for basic token-based APIs**.

When we consume an API there are two parts:
- frontend
- backend

They interact through an URL.

Our data does not get exposed.

The tokens are stored in the table `personal_access_tokens` When we log out, we must delete all the tokens associated with an user.

Usamos el middleware con sanctum para proteger todas las rutas.
```php
Route::middleware('auth:sanctum')->group(function () {

    Route::get('tasks', [TaskController::class, 'index']);

    Route::post('tasks', [TaskController::class, 'store']);

    Route::put('tasks/{id}', [TaskController::class, 'update']);

    Route::delete('tasks/{id}', [TaskController::class, 'destroy']);

});
```

