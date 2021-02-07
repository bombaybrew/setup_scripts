## Docker-compose for postgres + adminer

```
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
