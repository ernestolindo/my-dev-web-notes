# **PHP & MySQL - Tarea de alojamientos**

## **Roles y Tareas**

1. **Gestión de la Base de Datos y Conexión** (Ernesto):
    
    - Crear el esquema de la base de datos en MySQL, con las siguientes tablas básicas:
        - `users`: para almacenar los datos de los usuarios (id, nombre, correo, contraseña, tipo de usuario).
        - `lodgings`: para los alojamientos (id, nombre, descripción, imagen, etc.).
        - `user_lodgings`: tabla intermedia para relacionar usuarios con alojamientos seleccionados.
    - Configurar la conexión a la base de datos en PHP (crear un archivo reusable como `db.php`).
    - Implementar consultas básicas (SELECT, INSERT, DELETE) como funciones reutilizables.
2. **Diseño y Desarrollo de la Landing Page** (Persona 2):
    
    - Crear la interfaz principal de la landing page con HTML, CSS y Bootstrap (u otro framework).
    - Implementar la funcionalidad para cargar y mostrar los alojamientos desde la base de datos usando PHP.
    - Asegurarse de que el diseño sea atractivo y que los datos se muestren correctamente.
3. **Registro e Inicio de Sesión** (Persona 3):
    
    - Crear el formulario de registro e inicio de sesión.
    - Implementar validaciones tanto en el frontend (JavaScript) como en el backend (PHP).
    - Usar funciones de PHP para manejar el hashing de contraseñas (`password_hash`, `password_verify`).
    - Implementar sesiones para que los usuarios permanezcan autenticados después de iniciar sesión.
4. **Vista de Cuenta de Usuario** (Persona 4):
    
    - Crear la interfaz de la vista de cuenta del usuario.
    - Implementar la funcionalidad para que el usuario pueda ver y seleccionar alojamientos.
    - Usar PHP y MySQL para guardar las selecciones en la tabla `user_lodgings`.
    - Mostrar los alojamientos seleccionados por el usuario en esta vista.
5. **Rol de Administrador y Gestión de Alojamientos** (Persona 5):
    
    - Crear la funcionalidad para que el administrador pueda agregar nuevos alojamientos a la base de datos (formulario con validaciones y archivo PHP para insertar en la tabla `lodgings`).
    - Implementar la lógica que diferencia usuarios normales del administrador (usando el campo `tipo de usuario` en la tabla `users`).
    - Probar los privilegios del administrador para asegurarse de que no puede eliminar alojamientos.


| #rol | Rol                                            | Encargado |
| ---- | ---------------------------------------------- | --------- |
| 1    | Gestión de la Base de Datos y Conexión         |           |
| 2    | Diseño y Desarrollo de la Landing Page         |           |
| 3    | Registro e Inicio de Sesión                    |           |
| 4    | Vista de Cuenta de Usuario                     |           |
| 5    | Rol de Administrador y Gestión de Alojamientos |           |

**Flujo de trabajo**: 1-2 -> 3 -> 4-5