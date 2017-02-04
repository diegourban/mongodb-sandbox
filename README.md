# mongodb-sandbox
Sandbox for mongodb

sudo service mongod start

sudo service mongod stop

sudo service mongod restart

mongo

help

show dbs

show collections

db.alunos.find()

db.alunos.find().pretty()

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

