**Lazy loading**: cargar el elemento hasta que podamos acceder a el para mejorar el performance.

**Preload** para cargar lo que requerimos inmediatamente lo antes posible. De otra forma el navegador ira descargando las líneas de código según su orden.

Usamos **link** con el atributo **prefetch** para hacer que el navegador le descargue el usuario la pagina que es mas probable que visite a continuación.

El formato de imagen **webp** es hasta tres veces mas ligero que los formatos mas populares. Podemos establecerlo por medio de la etiqueta `<source>` anidada dentro de la etiqueta `<picture>`.

En el CSS no podemos hacer un **if...else** para mostrar una **webp** o una **jpg**, pero podemos auxiliarnos de JavaScript, particularmente de la biblioteca Modernizr, la cual nos ayuda a detectar la disponibilidad de funciones HTML, CSS y JavaScript en el navegador de un usuario.