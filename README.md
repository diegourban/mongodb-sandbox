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

