# Comandos
```md
# Para ver las bases de datos
show dbs

# para ver la base de datos actual
db

# crear base de datos
# para que se cree minimo se tiene que ingresar un dato
use NOMBREBD

# para ver la coleccion de la base de datos actual
show collections

# para eliminar la base de datos actual
db.dropDatabase()

# para crear una coleccion 
db.createCollection("NOMBRECOLECCION")

# para eliminar colecciones 
db.NOMBRECOLECCION.drop()

# para ver los datos
de.COLECCION.find()
de.COLECCION.find().pretty() #se ve mas bonito
```

```md
# Como se ingresan los datos - objetojson
{
	"nombre": "laptop",
	"precio": 40.2,
	"active". true,
	"creadoen": "12/5/2022",
	"somedate": [1, "a", []],
	"fabricante": {
		"name": "dell",
		"version": "xps"
	}
}
```

```md
# manejo de datos

# para ingresar datos
db.productos.insert(
	{
		"name": "laptop"
	}
)

# multiples datos
db.productos.insert([
	{
		"name": "laptop"
	},
	{
		"name": "nortebook"
	}
])

# buscar dato
db.productos.find({name: "laptop"})

# multiple busqueda
db.productos.find({name: "laptop"}, "precio": 999.99)

# solo el primer dato
db.productos.findOne({name: "laptop"})


# para ver datos precisos
db.productos.findOne({"name": "laptop"}, {"name": 1, "_id": 0})
```

**Coneccion mongodb**
```md
use crud

db.personas.insert({
	"nombre": "Cristobal"
	"apellido": "Sandoval"
})

db.createUser({
	user : "mongoadmin",
	pwd : "123456",
	roles : [
		{ role : "readWrite", db : "crud"}
	]
})

# por consola
mongo -u mongoadmin -p 123456 --authenticationDatabase crud
```