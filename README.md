# mongodb-sandbox
Sandbox for mongodb

## Requirements
MongoDB Installed

## Usage
`sudo service mongod start` - to start mongodb

`sudo service mongod stop` - to start mongodb

`sudo service mongod restart` - to restart mongodb

`mongoimport --db example --collection example --file file.json` - to import some collection to some database from some file

`mongoexport --db example --collection example --out file.json` - to export some collection from some database to some file

`mongo` - to connect to mongodb

`show dbs` - show the databases

`use test` - to use the test database

`show collections` - show the collections

`db.collection.find()` - to find everything from some collection

`db.collection.find().pretty()` - to find everything from some collection and show it is a pretty way

## Specific alunos collection commands

`db.alunos.find({
  nome: "Felipe"
})`


`db.alunos.find({
  nome : "Felipe",
  data_nascimento: new Date(1994, 02, 26)
})`


`db.alunos.find({
  curso.nome: "Sistemas de informação"
})`


`db.alunos.find({
  nome : "Felipe",
  curso.nome: "Sistemas de informação"
})`


`db.alunos.find({
  "habilidades.nome" : "inglês"
})`


`db.alunos.find({
  $or : [
    {"curso.nome" : "Sistemas de informação"},
    {"curso.nome" : "Engenharia Química"}
  ]
})`


`db.alunos.find({
  $or : [
    {"curso.nome" : "Sistemas de informação"},
    {"curso.nome" : "Engenharia Química"}
  ],
  "nome" : "Daniela"
})`


`db.alunos.find({
  "curso.nome" : {
    $in : ["Sistemas de informação", "Engenharia Química"]
  }
})`


`db.alunos.update(
  {"_id": ObjectId("1234565435")},
  {"nome" : "Toma cuidado"}
)` - will update all the data from the first occurence


`db.alunos.update(
  {"curso.nome" : "Sistema de informação"},
  { $set : 
    {"curso.nome" : "Sistemas de informação"}
  }
)` - will set the curso.nome from the first occurence


`db.alunos.update(
  {"curso.nome" : "Sistema de informação"},
  { $set : 
    {"curso.nome" : "Sistemas de informação"}
  }, {
    multi : true
  }
)` - to set the curso.nome from all occurences


`db.alunos.update(
  {"_id": ObjectId("1234565435")},
  { $push : 
    {notas : 8.5}
  }
)` - to add an element to notas array


`db.alunos.update(
  {"_id" : ObjectId("76a78d876bc6c867q6")},
  { $push : 
    {notas : [8.5, 3]}
  }
)` - to insert an array inside notas array


`db.alunos.update(
  {"_id" : ObjectId("76a78d876bc6c867q6")},
  { $push : 
    {notas : {$each : [8.5, 3]}}
  }
)` - to insert each element from the array to notas array

`db.alunos.find({notas:{$gt : 2}})` - find someone with notas greater than 2

`db.alunos.findOne({notas:{$gt : 5}})` - find only one

`db.alunos.find().sort({"nome" : 1})` - find and sort the elements in asc(1) order

`db.alunos.find().sort({"nome" : -1})` - find and sort the elements in desc(-1) order

`db.alunos.find().sort({"nome" : 1}).limit(3)` - find and sort the elements in asc(1) order limited to three results



