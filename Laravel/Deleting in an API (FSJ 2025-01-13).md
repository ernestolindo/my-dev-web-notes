Destroy function:
```php
public function destroy(Task $task, string $id)

    {

        // Buscar la tarea por el id

        $task = Task::findOrFail($id);

  

        // Eliminar la tarea

        $task->delete();

  

        return response()->json([

            'message' => 'Task deleted successfully'

        ]);

    }
```

Route:
```php
Route::delete('tasks/{id}', [TaskController::class, 'destroy']);
```