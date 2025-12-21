

`vim docker-compose.yml`

```bash
services:
  observium-db:
    image: mariadb:10.5
    container_name: observium-db
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: KToonXwd15Xqbz
      MYSQL_DATABASE: observium
      MYSQL_USER: observium_user
      MYSQL_PASSWORD: KToonXwd15Xqbz
    volumes:
      - observium-db-data:/var/lib/mysql
    networks:
      - observium_network

  observium:
    image: mbixtech/observium:latest
    container_name: observium
    restart: always
    depends_on:
      - observium-db
    environment:
      PUID: 1000
      PGID: 1000
      TZ: America/New_York
      OBSERVIUM_DB_HOST: observium-db
      OBSERVIUM_DB_USER: observium_user
      OBSERVIUM_DB_PASS: KToonXwd15Xqbz
      OBSERVIUM_DB_NAME: observium
    ports:
      - "8000:80"
    volumes:
      - observium-data:/config
    networks:
      - observium_network

volumes:
  observium-db-data:
  observium-data:

networks:
  observium_network:
```
```sh
docker-compose exec observium bash
docker exec -it observium bash

```
```./adduser.php admin mySecurePass123 10 ```
```./passwd.php admin newStrongerPass456```

