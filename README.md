# MongoDB-commands
example:compte operations | employes

db.comptes.insert({idCompte:'c99',solde:999})
db.comptes.insert([{idCompte:'c111',solde:1.11},{idCompte:'c222',solde:2.22}])
db.comptes.find().forEach(function(doc){
printjson('this is the solde: '+doc.solde+' this is the id: '+doc.idCompte)
})
db.comptes.find({idCompte:'c6',solde:100})
db.comptes.find({solde:{$gte:655}})
db.comptes.update({idCompte:'c6'},{$set:{solde:600}})
db.comptes.remove({idCompte:null})

db.operations.find()
db.operations.remove({})



db.employees.find()
db.employees.insert({id:'e2',name:'bouazid',travaux:[{name:'morrocan',status:'2'},{name:'tunisian',status:'1'}]})

db.employees.find({id:'e2'}).forEach(function(doc){
   printjson('id: '+doc.id+' -- name: '+doc.name)
   cursor=doc.travaux
   cursor.forEach(function(travail){
      printjson(travail.name+'---'+travail.status)
   })
})
