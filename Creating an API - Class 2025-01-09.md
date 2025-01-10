Creating `routes/api.php`
```powershell
php artisan install:api
```

## **Showing tasks**

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

## **Creating a new task**

Route to create a new task
```powershell
Route::post('tasks', [TaskController::class, 'store']);
```

Controller
```powershell
public function store(Request $request)

    {

        $task = Task::create($request->all());

  

        // retornamos un mensaje y el objeto creado

        return response()->json([

            'message' => 'Task created successfully',

            'data' => $task

        ], 201);

    }
```

