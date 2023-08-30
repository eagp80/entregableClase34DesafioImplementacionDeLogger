
# CORRESPONDE  A ENTREGABLE CLASE 32. Desafio: Implementacion de logger.
###  RUTAS
        - Ruta de inicio, de entrada a la api (redirige al login): 
        http://localhost:8000/api/v1/

        - Ruta de usuario actual logueado (muestra usuario examinando token):
        http://localhost:8000/api/v1/session/current

        - Ruta de usuario actual logueado por id (muestra usuario examinando BD en Mongo Atlas):
        http://localhost:8000/api/v1/session/current/:uid

###  SERVIDOR DE PRODUCTOS Y CARRITOS CON EXPRESS, VISTAS CON EXPRESS-HANDLEBARS, BASE DE DATOS MANEJADA CON MONGOOSE HACIA MONGO ATLAS (PRONTO TENDRÁ WEBSOCKET PARA CHAT CON SOCKETS.IO). 
### ADEMÁS TIENE: MANEJO DE VARIABLES DE ENTORNO CON dotenv CAMBIO DE VARIABLES DE ENTORNO DURANTE EJECUCIÓN CON cross-env, SE MUESTRAN RUTAS EN TABLA EN CONSOLA LADO BACKEND CON express-routemap, (PRONTO TENDRÁ MANEJO DE ARCHIVOS CON MULTER).

### Como usar la app:
<h2> Ruta de inicio, de entrada a la api:   </h2>
<h4> http://localhost:8000/api/v1/  la cual redirige al login </h4>

 <h2>Ejemplos de rutas:</h2>
        Ruta de inicio, de entrada a la api (redirige al login): 
        http://localhost:8000/api/v1/

        Ruta de usuario actual logueado:
        http://localhost:8000/api/v1/session/current

        Ruta de usuario actual logueado por id:
        http://localhost:8000/api/v1/session/current/:uid

        Para obtener todos los productos detalladamemnte en formato JSON (método GET)::
        http://localhost:8000/api/v1/products/

        Para ver resumen de todos los carritos (método GET):
        http://localhost:8000/api/v1/views/carts/

        Para la paginación desde mongo atlas con limit, sort y query (método GET):
        http://localhost:8000/api/v1/views/products?page=1&limit=3&sort={"code":1}&query={"description": "Desde fromulario con socket"}
## Consigna. Se está requiriendo lo siguiente:
- Basado en nuestro proyecto principal, implementar un logger.

### TESTEO:
- Se revisará que la estructura del servidor en general esté implementada con el logger de winston.
- Se ejecutará el proyecto en entorno de desarrollo y entorno productivo para corroborar que se implementen los diferentes loggers según el entorno.
- Se probará un endpoint (proporcionado por el alumno). para revisar que los logs se escriban correctamente, tanto para consola (desarrollo) como para consola y archivos (productivo).


### Formato

- Link al repositorio de Github con el proyecto completo, sin la carpeta de node_modules. ((Hecho)).

### Sugerencias
- La ruta loggerTest es muy importante para que tu entrega pueda ser calificada de manera rápida y eficiente. ¡No olvides colocarla!

### Aspectos a incluir
-Primero, definir un sistema de niveles que tenga la siguiente prioridad (de menor a mayor):
debug, http, info, warning, error, fatal.
- Después implementar un logger para desarrollo y un logger para producción, el logger de desarrollo deberá loggear a partir del nivel debug, sólo en consola.
- Sin embargo, el logger del entorno productivo debería loggear sólo a partir de nivel info.
- Además, el logger deberá enviar en un transporte de archivos a partir del nivel de error en un nombre “errors.log”.
- Agregar logs de valor alto en los puntos importantes de tu servidor (errores, advertencias, etc) y modificar los console.log() habituales que tenemos para que muestren todo a partir de winston.
- Crear un endpoint /loggerTest que permita probar todos los logs.

## Rutas para servidor con file-system en puerto 8081 (se deshabilito, es decir, se comentó en el código):

- Carritos: (se deshabilitó, es decir, se comentó en el código):
    - /api/carts/:cid   GET_BY_CID  trae carrito cid en formato JSON.
    - /api/carts/   POST crea un carrito nuevo vacío.
    - /api/carts/:cid/product/:pid  POST agregar producto pid a carrito cid.
    - En api/carts/  No hay PUT ni DELETE.

- Productos:(se deshabilitó, es decir, se comentó en el código):
    - /api/products/:pid GET_BY_PID muestra carrito pid en formato JSON, PUT con postman body y params, DELETE con postman y params.
    - /api/products/ GET de todos los productos en formato JSON y no hay formulario, POST con postman y body.
    - /api/products?limit=NUM GET muestra los primeros NUM productos en formato JSON. Utiliza req.query.

    - Adicionalmente, en localhost:8081/index2.html se tiene un formulario html para hacer POST de product.

- Socket IO:(se deshabilitó, es decir, se comentó en el código):
    - /    GET    Tiene socket. Utiliza vista "home.handlebars" y muestra lista de todos los productos en html. No tiene formulario.
    - /realtimeproducts  GET   Tiene socket. Utiliza vista "realTimeProducts.handlebars" y Tiene formulario para hacer post de product, muestra Lista de productos, al crear un producto nuevo lo muestra resaltado en una tabla y agrega al final de la lista mostrada el nuevo producto en html.

## Rutas para servidor con Mongo-Atlas en puerto 8000:

# Rutas carritos con Mongo:

- Ver la imagen en carpeta: imagenes explicativas.

# Rutas productos con Mongo:

-  Ver la imagen carpeta: imagenes explicativas.

# Rutas de  views (carritos y productos) con Mongo: 

- Ver la iamgen en carpeta carpeta: imagenes explicativas.
