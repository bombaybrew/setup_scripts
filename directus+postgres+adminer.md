## Directus + Postgres + Adminer


```
version: '3.8'

services:
  database:
    container_name: postgres
    image: postgres
    volumes:
      - ./data/database:/var/lib/postgresql/data
    networks:
      - mac-docker-network
    environment:
      POSTGRES_USER: '<admin_user>'
      POSTGRES_PASSWORD: '<admin_pass>'
      POSTGRES_DB: '<db_name>'
    ports:
      - <port>:5432
    volumes:
      - </Users/.../postgres>:/var/lib/postgresql/data/

  adminer:
    image: adminer
    container_name: adminer
    restart: always
    ports:
      - <port>:8080
    networks:
      - mac-docker-network

  directus:
    container_name: directus
    image: directus/directus:v9.0.0-rc.34
    ports:
      - <port>:8055
    networks:
      - mac-docker-network
    depends_on:
      - database
    environment:
      KEY: '<key>'
      SECRET: '<secret>'

      DB_CLIENT: 'pg'
      DB_HOST: host.docker.internal
      DB_PORT: 'db_port' # from database section
      DB_DATABASE: 'db_name' # from database section
      DB_USER: '<admin_user>' # from database section
      DB_PASSWORD: '<admin_pass>' # from database section

      CACHE_ENABLED: 'false'

      ADMIN_EMAIL: 'admin@example.com'
      ADMIN_PASSWORD: '<admin_email_pass>'

networks:
  mac-docker-network:
  ```
