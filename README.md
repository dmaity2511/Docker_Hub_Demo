- Note: USERNAME and PASSWORD hard-coded for Demo Purposes!
- mongo username=root password=password
- docker volume/k8 pv path= /data/db
- port no, web-server=80, app-server=3000, mongo-db=27017
- port forwarding is needed for local env


Port forwarding is needed
- kubectl port-forward service/web-server 80:80
- kubectl port-forward service/app-server 3000:3000
-  kubectl port-forward service/mongo 27017:27017

Follow below steps to provide input data to mongo-db
- docker exec -it <mongo container name> bash
- kubectl exec -it <mongo pod name> -- /bin/bash

- mongosh "mongodb://localhost:27017" --username root --authenticationDatabase admin
- give password when prompted 
- use contacts-db (command to create database in mongo db, this dbname is hardcoaded in app)
- db.contacts.insert({name:"Debjyoti", email:"dm@prime.com", cell:"9701533815"}) 
