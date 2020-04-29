# Comandos básicos de Mongodb

_He realizado este documento para que los interesados en Mongodb puedan saber los comandos básicos._

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

### Comandos Crear 📌

_Crea una db, esta no saldrá cuando ejecutemos el comando **show dbs** hasta que se inserte algo._

```
use.db_name  / use.almacen
```
_Crea una colección, aquí tenemos dos formas. En la primera le decimos cómo se va a llamar la colección, y en la segunda además de crear la colección, también le metemos las tuplas con sus datos._

```
db.name_collection.insert({"tupla":"data"})  / db.producto.insert({"nombre": "monitor"})
db.createCollection("name_collection") / db.createCollection("producto")
```




# 🛠️🛠️🛠️🛠️🛠️EN CONSTRUCCIÓN 🛠️🛠️🛠️🛠️🛠️




