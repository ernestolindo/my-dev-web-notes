En la migración de post:
```php
$table->foreignId('user_id')->constrained('users', 'id')->onDelete('cascade')->onUpdate('cascade');
```
Referenciar a una columna en otra tabla, donde:
- `constrained`: el nombre de la otra tabla, columna a la que estamos apuntando
- Al eliminar el id de usuario, eliminar el post
- Si se actualiza el id de usuario, actualizar en el post

También tenemos que hacer la relación de tablas en los modelos.

El post va a pertenecer a un solo usuario.

En el modelo post:
```php
public function user()

    {

        return $this->belongsTo(User::class);

    }
```

Pero un usuario puede tener más de un post.

En el modelo user:
```php

```