# Comandos básicos de Mongodb

_He realizado este documento para que los interesados en Mongodb puedan disponer de los comandos básicos._

## Conocimientos previos 📋

_Lo primero que hay que saber es que vamos a tener una base de datos (**DB**), esta base de datos a su vez va a contener colecciones (**Collections**), y estas colecciones van a estar compuestas por documentos (**Documents**). Estos documentos son en formato BSON, que no es más que una extensión de JSON que se representa de manera binaria.
Los documentos de una colección no tienen porque compartir la misma estructura, aunque en general sí que lo harán._

### Comandos generales 📌

_Muestra la DB con la que estamos trabajando actualmente._

```
db
```
_Muestra las DBs, por defecto vienen tres (admin, config , local) que tienen el funcionamiento interno de Mongodb._

```
show dbs
```
_Muestra los comandos que puedo utilizar, básicamente una ayuda por si te encuentras un poco perdido._

```
help
```
_Muestra todos los métodos posibles para la db._

```
db.help()
```
_Muestra la colección de la db actual._

```
show collections
```
_Muestra el número de documentos que tiene la colección._

```
db.collection_name.count()
```

### Comandos Crear 🛠️

_Crea una db, esta no saldrá cuando ejecutemos el comando **show dbs** hasta que se inserte algo._

```
use.db_name  / use.almacen
```
_Crea una colección, aquí tenemos dos formas. En la primera le decimos cómo se va a llamar la colección, y en la segunda además de crear la colección, también le metemos las tuplas con sus datos._

```
db.collection_name.insert({"tupla":"data"})  / db.producto.insert({"nombre": "monitor"})
db.createCollection("collection_name") / db.createCollection("producto")
```

### Comandos Eliminar ❌

_Elimina la db actual._

```
db.dropDatabase()
```
_Elimina una colección de la db actual._

```
db.collection_name.drop() / db.producto.drop()
```
_Elimina un documento concreto dependiendo de la tupla._

```
db.collection_name.remove({"tupla":"data"}) / db.producto.remove({"nombre":"monitor"})
```
_Elimina todos los documentos de la db._

```
db.collection_name.remove({}) / db.producto.remove({})
```

### Comandos Consulta 🔍

_Busca todos los datos que tiene una colección._

```
db.collection_name.find() / db.producto.find()
```
_Busca todos los datos que tiene una colección y los muestra de forma bonita._

```
db.collection_name.find().pretty() / db.producto.find().pretty()
```
_Para hacer una consulta, es tan sencillo como hacer lo siguiente. Además, dentro del find() se pueden añadir múltiples atributos._

```
db.collection_name.find({"tupla":"data"}) / db.producto.find({"producto":"monitor"})
```
_Devuelve un documento, este será el primero que esté en la colección._

```
db.collection_name.findOne() / db.producto.findOne()
```
_Realiza una consulta en la que busca el documento que tiene 'tupla: data', pero sólo muestra las tuplas 1 y 2. Esto siempre va a devolver el id, pero se puede quitar añadiendo '_id: 0' despues de 'tupla2: 1'._

```
db.collection_name.findOne({"tupla":"data"},{"tupla1": 1 , "tupla2": 1}) / db.producto.findOne({"nombre":"monitor"},{"categoria": 1 , "año": 1})
```
_Muestra los documentos que tengan "tupla: data", pero los ordena alfabéticamente por la tupla1._

```
db.collection_name.find({"tupla":"data"}).sort({"tupla1": 1}) / db.producto.findOne({"nombre":"monitor"}.sort({"categoria": 1})
```
_Devuelve tantos datos como pidamos, suele servir para mostrar las publicaciones más novedosas_

```
db.collection_name.find().limit(n) / db.producto.find().limit(2)
```
_Recorre los elementos de una colección y va uno a uno (forEach) pintando por pantalla lo que se quiera mostrar ._

```
db.collection_name.find().forEach(collection_name => print("Collection_name Name": + collection_name.name) / db.producto.find().forEach(produtco => print("Producto Nombre": + producto.nombre)
```

### Comandos Actualizar ⚙️

_Reemplaza una tupla por otra. Se pueden eliminar y añadir varias cosas a la vez_

```
db.collection_name.update({"tupla":"data"},{"tupla1": "data"}) / db.producto.update({"nombre":"monitor"},{"nombrecito": "teclado"})
```
_Añade una tupla en un documento, el cual se le indica con otra tupla._

```
db.collection_name.update({"tupla":"data"},{$set: {"tupla1": "data"}}) / db.producto.update({"nombre":"monitor"},{$set: {"precio": 99}})
```
_En este caso,'{"tupla":"data"}' no existe. Por lo tanto lo que hace es agregarla con su dato y a su vez la otra tupla. _

```
db.collection_name.update({"tupla":"data"},{$set: {"tupla1": "data"}}, {upsert: true}) /  db.producto.update({"nombre":"monitor"},{$set: {"precio": 99}}, {upsert: true})
```
_Incrementa el valor de una tupla. _

```
db.collection_name.update({"tupla":"data"},{$inc: {"tupla1": valor_a_incrementar}}) /  db.producto.update({"nombre":"monitor"},{$inc: {"precio": 1}})
```
_Cambia el nombre de una tupla. _

```
db.collection_name.update({"tupla":"data"},{$rename: {"tupla": "tupla1"}}) /  db.producto.update({"nombre":"monitor"},{$rename: {"nombre": "apodo"}})
```



## Autor ✒️

* Con ❤️ por **Guille Vargas** - [GuilleVargas](https://github.com/GuilleVargas)

