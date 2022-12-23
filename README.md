# Entrega-9


## MongoDB

### Lista de comandos: 

## - Para Crear la Base de Datos:

*use ecommerce*

## - Crear colecciones "Mensajes" "Productos":

*db.createCollection("mensajes")*
*db.createCollection("productos")*

## - Agregando 10 productos con valores distintos a cada coleccion. EJ:

*db.productos.insertMany([{"nombre": "Escuadra", "precio":120, "foto": "https://cdn3.iconfinder.com/data/icons/education-209/64/ruler-triangle-stationary-school-256.png", "date": ISODate()}])*


## - Listar todos los documentos en las colecciones:

*db.productos.find()*
*db.mensajes.find()*

## - Mostrar la cantidad de cada coleccion 

*db.productos.estimatedDocumentCount()*
*db.mensajes.estimatedDocumentCount()*


# Realizar CRUD sobre la coleccion Productos

## - Agregar un productos a la coleccion:

*db.productos.insertOne({}, {}, {}, {})*

## - Consultar por un nombre especifico:

*db.productos.find({nombre: "Adidas"})*

## - Listar los productos con precio menor $1000:

*db.productos.find({precio: {$lt: 1000}})*

## - Listar los productos con precio de $1000 a $3000:

*db.productos.find({$and:[{precio:{$gt:1000}},{precio: {$lt:3000}}]})*

## - Listar los productos con precio mayor $3000:

*db.productos.find({precio: {$gt: 3000}})*

## - Consultar que solamente traiga el nombre del tercer producto mas barato:

*db.productos.find({},{"nombre":1, "_id":0}).skip(2).limit(1).sort({precio: 1})*

## - Actualizar todos los productos, agregando al stock el valor de 100

*db.productos.updateMany({},{$set: {"stock":100}})*

## - Cambiar el stock a 0 de los productos con precio mayor $4000:

*db.productos.updateMany({precio:{$gt:4000}},{$set: {"stock":0}})*

## - Borrar los productos con precio menor $1000:

*db.productos.deleteMany({precio:{$lt: 1000}})*


## - Crea un usuario ("Pepe") clave ("asd456"), con permiso de lectura en la base de datos ecommerce

*use admin*
*db.createUser({user: "pepe", pwd: "asd456", roles: [{role: "read", db: "ecommerce"}]})*


## - Verificar que no pueda realizar ningun cambio












