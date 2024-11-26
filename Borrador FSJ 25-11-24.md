A Jairo lo agarró la loca xd

Tarea:
CRUD basico

funcionalidades especificas
- busqueda por titulo, autor o categoria - filtrar en el array 
- prestamo de libro si esta disponible

clases necesarias... ejemplos
- libro
- biblioteca

documentar...

enlace repo en github

principio de responsabilidad unica - codigo modular

array que sea una sesion

---

El dato GET de id de la URL viene como string, por eso no es lo mismo que el id guardado en el array, que es un numero.

---

Que el form nos deje editar un registro preexistente... cambiar el form

```
<?php

    if (isset($_GET['edit'])) {

        $aerolineaEditable = getAerolineaPorId($_GET['edit'], $aerolineas);

        echo "<pre>";

        print_r($aerolineaEditable);

        echo "</pre>";

    ?>

  

        <form method="POST" action="">

            <label>Nombre Aerolinea</label>

            <input type="text" name="nombre" value="<?php echo $aerolineaEditable->getNombre() ?>">

  

            <label>Cantidad de aviones</label>

            <input type="text" name="cantAviones" value="<?php echo $aerolineaEditable->getCant_aviones() ?>">

  

            <label>Tipo de aerolinea</label>

            <input type="text" name="tipoAerolinea" value="<?php echo $aerolineaEditable->getTipo_aerolinea() ?>">

  

            <button type="submit">Editar aerolinea</button>

        </form>

    <?php } ?>
```

Movimos la llavecita y se arreglo

...

if... else

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