# docker-nginx-drupal
A docker image with nginx and ready for drupal.
Based on [docker-nginx-wordpress](https://github.com/maxpowel/docker-nginx-wordpress)

# How to use
Just mount your drupal root in the directory `/var/www/html/drupal` and run it, for example:
```
docker run -it --rm -p 80:80 --network local -v /home/maxpowel/my_drupal:/var/www/html/drupal-10.0.0 --name drupal maxpowel/nginx-drupal
```
You need also a database:
```
docker run --rm --network local -e MYSQL_ROOT_PASSWORD=123456 --name mariadb mariadb --sql-mode="ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION"
```

And access to `http://localhost`

To get the database ip, you can use this command:
```
docker network inspect local
```
But you can use the docker container name as hostname


