# docker-compose-phpmyadmin
Simple docker-compose.yml for Laravel Sail apps that need phpMyAdmin

To add phpMyAdmin to existing Laravel Sail

```PHP
    phpmyadmin:
        depends_on:
            - mysql
        image: phpmyadmin/phpmyadmin
        environment:
            - PMA_HOST=mysql
            - PMA_POSRT=3306
        networks:
            - sail
        ports:
            - 8001:80
```

If having issues with port 80 on MAC, then

```
        ports:
            #- '${APP_PORT:-80}:80'
            - '8084:80'
            - '${HMR_PORT:-8080}:8080'
```

Credits to:

https://www.youtube.com/watch?v=AGg8UJoQGWk&t=3s



