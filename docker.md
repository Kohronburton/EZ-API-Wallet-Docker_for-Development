# Docker for [EzBitcoin API Wallet](https://github.com/Kohronburton/EzBitcoin-Api-Wallet)

### Steps to build app
1. Install docker and docker compose for your SO
2. Duplicate the file ***.env.example.php*** and rename to ***.env.php***
3. Build the images
````
docker-compose build
````
4. Start containers
````
docker-compose up -d
````
5. Install composer dependencies
````
docker-compose exec app composer install
````
6. Run migrations and seeds
````
docker-compose exec app php artisan migrate --seed
````
7. Enjoy your app on [https://localhost](https://localhost)

## Some helpful commands
### Enter postgreSQL container
````
docker-compose exec pgsql psql --dbname=ezbitapi --username=wallet-usr --password
````
````
Password: wallet-pwd
````
## NOTES
 - This script uses ports 80, 443, 5432, 8080, 8025 by default, so, be sure there aren't any app running on those ports or can be conflicts.
 - This script implements [adminer](https://www.adminer.org) as gui for databases, access on [http://localhost:8080](http://localhost:8080).
````
System: PostgreSql
Server: pgsql
Username: wallet-usr
Password: wallet-pwd
Databse: ezbitapi
````
- This script implements [mailhog](https://github.com/mailhog) as driver for mails, access on [http://localhost:8025](http://localhost:8025).


## REALIZED NOTES
- Updated the files app/config/database.php and app/config/mail.php to make the config variable
