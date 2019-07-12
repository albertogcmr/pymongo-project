# pymongo-project

## 1. Installation

### 1.1. Installation Mongo

Link: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/

1. Ejecutar en terminal una a una los siguentes comandos. 
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
echo "mongodb-org hold" | sudo dpkg --set-selections
echo "mongodb-org-server hold" | sudo dpkg --set-selections
echo "mongodb-org-shell hold" | sudo dpkg --set-selections
echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
echo "mongodb-org-tools hold" | sudo dpkg --set-selections
```

2. Comprobamos si el servicio funciona
```
sudo service mongod start
```
3. Comprobamos el log y debemos ver algo como **[initandlisten] waiting for connections on port 27017**
```
sudo cat /var/log/mongodb/mongod.log
```
4. Reiniciamos servicio
```
sudo service mongod stop
```
5. Iniciar servicio desde cero para dejarlo funcionando
```
sudo service mongod restart
mongo
```

### 1.2. Installation Compass
Link: https://docs.mongodb.com/compass/master/install/

1. descarga del link: https://www.mongodb.com/download-center/compass?jmp=hero
2. ejecuta el archivo descargado
3. Ahora tienes mongodb-compass entre tus programas


## 2. Importar base de datos a mongodb
1. iniciar mongodb 
```
sudo service mongod restart
```
2. Abrir compass en nuestro escritorio
3. create database (botón verde) y seleccionamos los campos Database name: db_companies, Collection name: companies. 
![](images/01-create-database.png)
![](images/02-create-database.png)
![](images/03-compass-mongo-companies.png)

4. importar a mongo el json que queremos: 
```
mongoimport --db db_companies --collection companies companies.json
```

## 3. pymongo y filtrado

Ahora abrimos un jupyter notebook
```
jupyter notebook
```
