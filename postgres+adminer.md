## Docker-compose for postgres + adminer

```
# pg_adminer.yml
version: '3.8'

services:
  db:
    image: postgres
    container_name: postgres
    restart: always
    environment:
      POSTGRES_USER: <admin_user>
      POSTGRES_PASSWORD: <secret_password>
    ports:
      - <host_port>:5432
    volumes:
      - /Users/..../postgres:/var/lib/postgresql/data/

  adminer:
    image: adminer
    container_name: adminer
    restart: always
    ports:
      - <host_port>:8080
```

```
> docker-compose -f pg_adminer.yml up

----
Creating adminer  ... done
Creating postgres ... done
Attaching to adminer, postgres
adminer    | [Sun Feb  7 05:24:38 2021] PHP 7.4.15 Development Server (http://[::]:8080) started
postgres   | The files belonging to this database system will be owned by user "postgres".
postgres   | This user must also own the server process.
postgres   | 
postgres   | The database cluster will be initialized with locale "en_US.utf8".
postgres   | The default database encoding has accordingly been set to "UTF8".
postgres   | The default text search configuration will be set to "english".
postgres   | 
postgres   | Data page checksums are disabled.
postgres   | 
postgres   | fixing permissions on existing directory /var/lib/postgresql/data ... ok
postgres   | creating subdirectories ... ok
postgres   | selecting dynamic shared memory implementation ... posix
postgres   | selecting default max_connections ... 100
postgres   | selecting default shared_buffers ... 128MB
postgres   | selecting default time zone ... Etc/UTC
postgres   | creating configuration files ... ok
postgres   | running bootstrap script ... ok
postgres   | performing post-bootstrap initialization ... ok
postgres   | syncing data to disk ... ok
.
.
.
postgres   | 2021-02-07 05:24:53.091 UTC [1] LOG:  database system is ready to accept connections
```
