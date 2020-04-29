# Comandos básicos de Mongodb

_He realizado este documento para que los interesados en Mongodb puedan disponer de los comandos básicos._

## Conocimientos previos 📋

_Lo primero que hay que saber es que vamos a tener una base de datos (**DB**), esta base de datos a su vez va a contener colecciones (**Collections**), y estas colecciones van a estar compuestas por documentos (**Documents**). Estos documentos son en formato BSON, que no es más que una extensión de JSOn que se representa de manera binaria.
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

# 🛠️🛠️🛠️🛠️🛠️EN CONSTRUCCIÓN 🛠️🛠️🛠️🛠️🛠️




