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

## Editar un registro

1. Crear un botón de edición para cada registro que al ser presionado pase el ID correspondiente como valor del parámetro `edit` en el query string de la URL.
2. Crear un formulario de edición.
4. Si existe la llave `edit` en el superglobal `$_GET`, obtener el objeto de la aerolínea correspondiente usando el método mostrar el formulario de edición. Si no, mostrar el formulario de creación.

--- 

si hubieramos hecho los modulos en otra vista lo que cargariamos seria el require...



> [!This is a note] This is the title
> Disfruta este día como si fuera el último... el futuro está sobrevalorado.

---

el form de editar crea un nuevo registro. 

problema con el post

enviar el tipo de form con el submit 

```
if (isset($_POST['createForm'])) {
```

task: autocorrect y/n

---

encontrar la aerolínea a actualizar y cambiarle los valores.

```
if ($aerolinea->getId() == $_POST['id']) {
```

comparamos el id del objeto con el id del POST

---

clase para definiciones... getters y setters
y 
clase para CRUD

## eliminar una aerolinea

```

if (isset($_GET['delete'])) {

    $idDelete = $_GET['delete'];

    foreach ($aerolineas as $key => $aerolinea) {

        if ($aerolinea->getId() == $idDelete) {

            unset($aerolineas[$key]);

            break; // salir del bucle

        }

    };

}
```

como se usa el unset?
explica eso....

explica el foreach...

para que esta linea...
$_SESSION['aerolineas'] = $aerolineas;

por qué solo para el delete y no para el edit?