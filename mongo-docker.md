## Setup
```
$ docker volume create --opt type=none --opt device=/srv/volume/mongodb mongo_volume

$ docker run 
    -v mongo_volume:/data/db -p 27777:27017 
    --name mymongo 
    -e MONGO_INITDB_ROOT_USERNAME=<admin_user> 
    -e MONGO_INITDB_ROOT_PASSWORD=<password> 
    -d mongo mongod 
    --auth
```
