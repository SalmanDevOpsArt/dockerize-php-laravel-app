PERMISSION DENIED ISSUE.
HOW TO SOLVE THIS:

> docker exec -it <container-name> sh (access inside php container)

Fixing permission:
> chown -R www-data:www-data /var/www/html/storage /var/www/html/bootstrap/cache
>chmod -R 775 /var/www/html/storage /var/www/html/bootstrap/cache

 (Base table not found issue):
Create database table:

> docker exec -it <php-container-name> php artisan session:table
> docker exec -it <php-container-name> php artisan migrate

NOW IT WORKS....