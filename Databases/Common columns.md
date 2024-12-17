Columns in different tables that are related or linked. These columns **don’t have to share the same name** but must contain **related data** that can be used to match rows between the tables.

```mysql
SELECT productos.nombre
FROM productos 
JOIN productos_ordenes ON productos.id = productos_ordenes.id_producto
```

**"Common columns"** are:

1. `productos.id` in the `productos` table
2. `productos_ordenes.id_producto` in the `productos_ordenes` table

The column names are different (`id` and `id_producto`), but they represent the **same kind of information**—the product ID. That’s what allows SQL to "connect" the two tables.

### Why Use "Common Columns" in `ON`?

The `ON` condition **tells SQL how to match rows** between tables. SQL does this by comparing the values in these "common columns."

- If the values **match**, the rows are combined.
- If there’s no match, the row is excluded (unless you use other joins like `LEFT JOIN`, but that’s for later).