# **Redirecting URLs to index.php - htaccess**

En tu aplicación, necesitas que todas las URLs pasen por `index.php` para que el enrutador determine qué controlador y método ejecutar. Para ello, necesitas crear un [[htaccess]].

```
Options -Indexes
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php?url=$1 [QSA,L]
```

#### 1. **`Options -Indexes`**

Esto desactiva el listado de directorios.  
Si no tienes un archivo como `index.php` en una carpeta, el servidor Apache podría mostrar una lista de todos los archivos en esa carpeta. Este comando evita que eso suceda, mejorando la seguridad.

#### 2. **`RewriteEngine On`**

Esto activa el **motor de reescritura de URLs** en Apache. Permite que se apliquen reglas personalizadas para manejar las solicitudes de los usuarios.

#### 3. **`RewriteCond %{REQUEST_FILENAME} !-f`**

Esta línea verifica si el archivo solicitado **NO** es un archivo físico en el servidor.

- Por ejemplo, si alguien solicita `http://localhost/style.css`, esta regla permite que el archivo `style.css` sea servido directamente y no se pase por el enrutador.

#### 4. **`RewriteCond %{REQUEST_FILENAME} !-d`**

De manera similar, esta regla verifica si la solicitud **NO** es una carpeta.

- Si alguien pide `http://localhost/public`, y existe la carpeta `public`, no redirigirá esa solicitud.

#### 5. **`RewriteRule ^(.*)$ index.php [L]`**

Esta es la regla principal que **redirige todas las demás solicitudes a `index.php`**.

- `^(.*)$`: Captura todo lo que se escriba en la URL.
- **`index.php?url=$1`**: Esto agrega el valor capturado por `(.*)` (el contenido de la URL después del dominio) como un parámetro en la URL que será accesible dentro de `index.php` usando `$_GET['url']`.
- **`[QSA]`**: Este flag significa "Query String Append", es decir, si la URL ya tiene parámetros de consulta (como `?foo=bar`), se conservarán y se agregarán a la nueva URL reescrita.
- `[L]`: Indica que esta es la última regla que debe evaluarse para esta solicitud.