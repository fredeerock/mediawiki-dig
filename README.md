Run with: `docker-compose up -d`

If the environmental variables are changed you have to...

`docker-compose stop && docker-compose rm && docker volume prune && docker system prune`

You also need a vars.env file with the below variables to store passwords. Make sure to include this in a .gitignore. 

```
MEDIAWIKI_WIKI_NAME=Wiki Name
MEDIAWIKI_PASSWORD=Wiki Password
MEDIAWIKI_DATABASE_PASSWORD=DB Pass
MARIADB_ROOT_PASSWORD=DB Root Pass
MARIADB_PASSWORD=DB Pass
SMTP_HOST=ssl://smtp.host.com
SMTP_HOST_ID=
SMTP_PORT=
SMTP_USER=
```