# pymongo-project

## Installation

### 1. Installation Mongo

Link: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/

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

Comprobamos si el servicio funciona
```
sudo service mongod start
```
Comprobamos el log y debemos ver algo como [initandlisten] waiting for connections on port 27017
```
sudo cat /var/log/mongodb/mongod.log
```
Reiniciamos servicio
```
sudo service mongod stop
```
Iniciar servicio desde cero
```
sudo service mongod restart
mongo
```