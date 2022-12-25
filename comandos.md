// 1) y 2)

//Productos

db.productos.insertMany([{nombre: "Mouse pad", precio: 1500}, {nombre: "Mouse", precio: 2000},{nombre: "Teclado", precio: 3100},{nombre: "Auriculares", precio: 3200},{nombre: "Monitor", precio: 4500}])
{
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("63a86ca96833621de086a4de"),
                ObjectId("63a86ca96833621de086a4df"),
                ObjectId("63a86ca96833621de086a4e0"),
                ObjectId("63a86ca96833621de086a4e1"),
                ObjectId("63a86ca96833621de086a4e2")
        ]
}
> db.productos.insertMany([{nombre: "Memoria Ram", precio: 2500}, {nombre: "Webcam", precio: 5000},{nombre: "Procesador", precio: 4900},{nombre: "Cable usb", precio: 150},{nombre: "Cable HDMI", precio: 400}])
{
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("63a86d496833621de086a4e3"),
                ObjectId("63a86d496833621de086a4e4"),
                ObjectId("63a86d496833621de086a4e5"),
                ObjectId("63a86d496833621de086a4e6"),
                ObjectId("63a86d496833621de086a4e7")
        ]
}

//Mensajes

> db.mensajes.insertMany([{usuario: "Santiago", mensaje: "Buen dia grupo!"}, {usuario: "Jorge", mensaje: "Buenass"},{usuario: "Maria", mensaje: "Holaa"},{usuario: "Fulano", mensaje: "Como va"},{usuario: "Nicolas", mensaje: "q onda"}])
{
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("63a86e536833621de086a4e8"),
                ObjectId("63a86e536833621de086a4e9"),
                ObjectId("63a86e536833621de086a4ea"),
                ObjectId("63a86e536833621de086a4eb"),
                ObjectId("63a86e536833621de086a4ec")
        ]
}
> db.mensajes.insertMany([{usuario: "Santiago", mensaje: "Nos juntamos para año nuevo?"}, {usuario: "Jorge", mensaje: "Yo no estoy amigo"},{usuario: "Maria", mensaje: "Dale"},{usuario: "Fulano", mensaje: "Si, donde?"},{usuario: "Nicolas", mensaje: "Yo pongo casa :) "}])
{
        "acknowledged" : true,
        "insertedIds" : [
                ObjectId("63a86ec16833621de086a4ed"),
                ObjectId("63a86ec16833621de086a4ee"),
                ObjectId("63a86ec16833621de086a4ef"),
                ObjectId("63a86ec16833621de086a4f0"),
                ObjectId("63a86ec16833621de086a4f1")
        ]
}

3)

// Productos

> db.productos.find()
{ "_id" : ObjectId("63a86ca96833621de086a4de"), "nombre" : "Mouse pad", "precio" : 1500 }
{ "_id" : ObjectId("63a86ca96833621de086a4df"), "nombre" : "Mouse", "precio" : 2000 }
{ "_id" : ObjectId("63a86ca96833621de086a4e0"), "nombre" : "Teclado", "precio" : 3100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e1"), "nombre" : "Auriculares", "precio" : "3200" }
{ "_id" : ObjectId("63a86ca96833621de086a4e2"), "nombre" : "Monitor", "precio" : 4500 }
{ "_id" : ObjectId("63a86d496833621de086a4e3"), "nombre" : "Memoria Ram", "precio" : 2500 }
{ "_id" : ObjectId("63a86d496833621de086a4e4"), "nombre" : "Webcam", "precio" : 5000 }
{ "_id" : ObjectId("63a86d496833621de086a4e5"), "nombre" : "Procesador", "precio" : 4900 }
{ "_id" : ObjectId("63a86d496833621de086a4e6"), "nombre" : "Cable usb", "precio" : 150 }
{ "_id" : ObjectId("63a86d496833621de086a4e7"), "nombre" : "Cable HDMI", "precio" : 400 }

// Mensajes

> db.mensajes.find()
{ "_id" : ObjectId("63a86e536833621de086a4e8"), "usuario" : "Santiago", "mensaje" : "Buen dia grupo!" }
{ "_id" : ObjectId("63a86e536833621de086a4e9"), "usuario" : "Jorge", "mensaje" : "Buenass" }
{ "_id" : ObjectId("63a86e536833621de086a4ea"), "usuario" : "Maria", "mensaje" : "Holaa" }
{ "_id" : ObjectId("63a86e536833621de086a4eb"), "usuario" : "Fulano", "mensaje" : "Como va" }
{ "_id" : ObjectId("63a86e536833621de086a4ec"), "usuario" : "Nicolas", "mensaje" : "q onda" }
{ "_id" : ObjectId("63a86ec16833621de086a4ed"), "usuario" : "Santiago", "mensaje" : "Nos juntamos para año nuevo?" }
{ "_id" : ObjectId("63a86ec16833621de086a4ee"), "usuario" : "Jorge", "mensaje" : "Yo no estoy amigo" }
{ "_id" : ObjectId("63a86ec16833621de086a4ef"), "usuario" : "Maria", "mensaje" : "Dale" }
{ "_id" : ObjectId("63a86ec16833621de086a4f0"), "usuario" : "Fulano", "mensaje" : "Si, donde?" }
{ "_id" : ObjectId("63a86ec16833621de086a4f1"), "usuario" : "Nicolas", "mensaje" : "Yo pongo casa :) " }


4)

// Productos

> db.productos.count()
10

// Mensajes 

> db.mensajes.count()
10


5)

a)
 
> db.productos.insertOne({nombre: "Fuente", precio: 3700})
{
        "acknowledged" : true,
        "insertedId" : ObjectId("63a870366833621de086a4f2")
}

b)

I) 

> db.productos.find({precio: {$lt: 1000}})
{ "_id" : ObjectId("63a86d496833621de086a4e6"), "nombre" : "Cable usb", "precio" : 150 }
{ "_id" : ObjectId("63a86d496833621de086a4e7"), "nombre" : "Cable HDMI", "precio" : 400 }

II)

> db.productos.find({$and: [{precio: {$gte: 1000}},{precio: {$lte: 3000}}]})
{ "_id" : ObjectId("63a86ca96833621de086a4de"), "nombre" : "Mouse pad", "precio" : 1500 }
{ "_id" : ObjectId("63a86ca96833621de086a4df"), "nombre" : "Mouse", "precio" : 2000 }
{ "_id" : ObjectId("63a86d496833621de086a4e3"), "nombre" : "Memoria Ram", "precio" : 2500 }

III)

> db.productos.find({precio: {$gt: 3000}})
{ "_id" : ObjectId("63a86ca96833621de086a4e0"), "nombre" : "Teclado", "precio" : 3100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e2"), "nombre" : "Monitor", "precio" : 4500 }
{ "_id" : ObjectId("63a86d496833621de086a4e4"), "nombre" : "Webcam", "precio" : 5000 }
{ "_id" : ObjectId("63a86d496833621de086a4e5"), "nombre" : "Procesador", "precio" : 4900 }
{ "_id" : ObjectId("63a870366833621de086a4f2"), "nombre" : "Fuente", "precio" : 3700 }

IV)

> db.productos.find({precio: 1500}, {nombre: 1, "_id": 0})
{ "nombre" : "Mouse pad" }


c)

> db.productos.updateMany({}, {$set: {stock: 100}})
{ "acknowledged" : true, "matchedCount" : 11, "modifiedCount" : 11 }

> db.productos.find()
{ "_id" : ObjectId("63a86ca96833621de086a4de"), "nombre" : "Mouse pad", "precio" : 1500, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4df"), "nombre" : "Mouse", "precio" : 2000, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e0"), "nombre" : "Teclado", "precio" : 3100, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e1"), "nombre" : "Auriculares", "precio" : "3200", "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e2"), "nombre" : "Monitor", "precio" : 4500, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e3"), "nombre" : "Memoria Ram", "precio" : 2500, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e4"), "nombre" : "Webcam", "precio" : 5000, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e5"), "nombre" : "Procesador", "precio" : 4900, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e6"), "nombre" : "Cable usb", "precio" : 150, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e7"), "nombre" : "Cable HDMI", "precio" : 400, "stock" : 100 }
{ "_id" : ObjectId("63a870366833621de086a4f2"), "nombre" : "Fuente", "precio" : 3700, "stock" : 100 }

d)

> db.productos.updateMany({precio: {$gte: 4000}}, {$set: {stock: 0}})
{ "acknowledged" : true, "matchedCount" : 3, "modifiedCount" : 3 }

> db.productos.find()
{ "_id" : ObjectId("63a86ca96833621de086a4de"), "nombre" : "Mouse pad", "precio" : 1500, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4df"), "nombre" : "Mouse", "precio" : 2000, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e0"), "nombre" : "Teclado", "precio" : 3100, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e1"), "nombre" : "Auriculares", "precio" : "3200", "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e2"), "nombre" : "Monitor", "precio" : 4500, "stock" : 0 }
{ "_id" : ObjectId("63a86d496833621de086a4e3"), "nombre" : "Memoria Ram", "precio" : 2500, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e4"), "nombre" : "Webcam", "precio" : 5000, "stock" : 0 }
{ "_id" : ObjectId("63a86d496833621de086a4e5"), "nombre" : "Procesador", "precio" : 4900, "stock" : 0 }
{ "_id" : ObjectId("63a86d496833621de086a4e6"), "nombre" : "Cable usb", "precio" : 150, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e7"), "nombre" : "Cable HDMI", "precio" : 400, "stock" : 100 }
{ "_id" : ObjectId("63a870366833621de086a4f2"), "nombre" : "Fuente", "precio" : 3700, "stock" : 100 }

e)

> db.productos.deleteMany({precio: {$lt: 1000}})
{ "acknowledged" : true, "deletedCount" : 2 }

> db.productos.find()
{ "_id" : ObjectId("63a86ca96833621de086a4de"), "nombre" : "Mouse pad", "precio" : 1500, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4df"), "nombre" : "Mouse", "precio" : 2000, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e0"), "nombre" : "Teclado", "precio" : 3100, "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e1"), "nombre" : "Auriculares", "precio" : "3200", "stock" : 100 }
{ "_id" : ObjectId("63a86ca96833621de086a4e2"), "nombre" : "Monitor", "precio" : 4500, "stock" : 0 }
{ "_id" : ObjectId("63a86d496833621de086a4e3"), "nombre" : "Memoria Ram", "precio" : 2500, "stock" : 100 }
{ "_id" : ObjectId("63a86d496833621de086a4e4"), "nombre" : "Webcam", "precio" : 5000, "stock" : 0 }
{ "_id" : ObjectId("63a86d496833621de086a4e5"), "nombre" : "Procesador", "precio" : 4900, "stock" : 0 }
{ "_id" : ObjectId("63a870366833621de086a4f2"), "nombre" : "Fuente", "precio" : 3700, "stock" : 100 }


// 6)
> use admin
switched to db admin

> db.createUser({user:"pepe", pwd:"asd456", roles:[{role: "read", db: "ecommerce"}]})
Successfully added user: {
        "user" : "pepe",
        "roles" : [
                {
                        "role" : "read",
                        "db" : "ecommerce"
                }
        ]
}