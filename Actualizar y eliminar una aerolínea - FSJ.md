# Actualizar y eliminar una aerolínea - FSJ

## Solución de mi error en la función `getAerolineaPorId()`

La variable **$id** obtenida desde la URL viene como **string**, mientras que el id guardado en el array es de tipo **number**, por ello se retorna FALSE al utilizar el operador de comparación estricto. Solución: ==utilizar el loose equality operator==.

```
function getAerolineaPorId($id, $aerolineas)

{

    foreach ($aerolineas as $aerolinea) {

        if ($aerolinea->getId() == $id) {

            return $aerolinea;

        }

    };

}
```

---

## Editar una aerolínea

1. Crear un botón de edición para cada registro que al ser presionado pase el ID correspondiente como valor del parámetro `edit` en el query string de la URL.
2. Crear un formulario de edición.
4. Si existe la llave `edit` en el superglobal `$_GET`, obtener el objeto de la aerolínea correspondiente usando el método `getAerolineaPorId()` y mostrar el formulario de edición. Si no, mostrar el formulario de creación.
5. Enviar una *flag* en el `$_POST` que identifique si el origen de los datos es el formulario de creación o el formulario de edición.
6. Sí y solo sí se envió el formulario de edición, recorrer el array de **aerolíneas**.
7. Sí el **id** de la aerolínea del array concuerda con el **id** enviando en el `$_POST`, utilizar los setters para reemplazar los datos actuales del objeto por los enviados en el form.

--- 
## Eliminar una aerolínea

1. Crear un botón de eliminación para cada registro que al ser presionado pase el ID correspondiente como valor del parámetro `delete` en el query string de la URL.
2. Si existe el parámetro `delete` en el superglobal `$_GET`, recorrer el array de **aerolíneas**.
3. Sí el **id** de la aerolínea del array concuerda con el **id** enviando en el `$_GET`, utilizar  la función `unset()` para eliminar el elemento del arreglo y salir del bucle con el `break` statement.
4. Reasignar el arreglo actualizado a `$_SESSION['aerolineas']` para que los cambios se reflejen en la sesión.
5. Redirigir con `header("Location: ")` para quitar el query string de la URL. 