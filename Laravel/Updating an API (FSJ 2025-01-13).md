Route to update an entry:
```php
Route::put('tasks/{id}', [TaskController::class, 'update']);
```

Update function in `TaskController`:
```php
public function update(Request $request, string $id)

    {

        $task = Task::findOrFail($id);

  

        $task->update($request->all());

        return response()->json([

            'message' => 'Task updaded successfully',

            'data' => $task

        ]);

    }
```