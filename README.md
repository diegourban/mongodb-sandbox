# mongodb-sandbox
Sandbox for mongodb

## Requirements
MongoDB Installed

## Usage
`sudo service mongod start` - to start mongodb

`sudo service mongod stop` - to start mongodb

`sudo service mongod restart` - to restart mongodb

`mongoexport --db test --collection alunos --out alunos.json` - to export the collection alunos from test db to alunos.json file

`mongo` - to connect to mongodb

`show dbs` - show the databases

`show collections` - show the collections

`db.collection.find()` - to find everything from some collection

`db.collection.find().pretty()` - to find everything from some collection and show it is a pretty way


db.alunos.find({
  nome: "Felipe"
})


db.alunos.find({
  nome : "Felipe",
  data_nascimento: new Date(1994, 02, 26)
})


db.alunos.find({
  curso.nome: "Sistemas de informação"
})


db.alunos.find({
  nome : "Felipe",
  curso.nome: "Sistemas de informação"
})


db.alunos.find({
  "habilidades.nome" : "inglês"
})


db.alunos.find({
  $or : [
    {"curso.nome" : "Sistemas de informação"},
    {"curso.nome" : "Engenharia Química"}
  ]
})


db.alunos.find({
  $or : [
    {"curso.nome" : "Sistemas de informação"},
    {"curso.nome" : "Engenharia Química"}
  ],
  "nome" : "Daniela"
})


db.alunos.find({
  "curso.nome" : {
    $in : ["Sistemas de informação", "Engenharia Química"]
  }
})

