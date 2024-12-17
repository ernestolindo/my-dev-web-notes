**Data Manipulation Language (DML)**

Después de crear la estructura de la tabla con DDL, trabajamos con los datos dentro de ella usando los comandos DML.

**No olvidar el USE:** Seleccionar nuestra base de datos
```mysql
USE empresa;
```

**Crear datos**:
```mysql
INSERT INTO productos (nombre, precio, cantidad, proveedor) VALUES 
("Teclado", 50, 5, "Keychron"), ("Monitor", 510, 15, "Lenovo");
```

**Leer datos**
```mysql
SELECT * FROM productos LIMIT 25;

# Leer un dato en particular
SELECT * FROM productos WHERE cantidad > 5;
```

**Actualizar un dato**:
```mysql
UPDATE productos SET precio = 100, cantidad = cantidad + 5 WHERE id = 1;
```