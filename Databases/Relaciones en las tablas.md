Las FOREIGN_KEY nos aseguran que los datos referenciados existen en la tabla correspondiente, es decir, que los datos sean reales. 

```mysql
CREATE TABLE productos_ordenes(
    id int AUTO_INCREMENT PRIMARY KEY,
    id_orden int NOT NULL,
    id_producto int NOT NULL,
    FOREIGN KEY (id_orden) REFERENCES ordenes(id),
    FOREIGN KEY (id_producto) REFERENCES productos(id)
);
```

**1 a 1**
> "Un empleado puede tener un solo sueldo"

**1 a muchos**
> "Un developer puede saber muchas tecnologías"

**muchos a muchos**
> "Una misma orden puede tener muchos productos y un mismo producto puede estar en muchas ordenes"

## Join

[[Joins]] combine records from two or more tables in a database.

```mysql
# JOIN
SELECT productos.nombre, ordenes.fecha_orden 
FROM productos 
# Traer los productos cuando aparezcan en productos_ordenes
JOIN productos_ordenes ON productos.id = productos_ordenes.id_producto
# Traer las ordenes cuando aparezcan en productos_ordenes
JOIN ordenes ON productos_ordenes.id_orden = ordenes.id;
```

Muchas veces necesitamos tablas intermedias como `productos_ordenes` que nos permitan relacionar dos tablas. No podríamos haber hecho el JOIN de arriba sin esa tabla.