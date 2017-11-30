Grab the docker-compose file with:  
`curl -sSL https://raw.githubusercontent.com/fredeerock/mediawiki-dig/master/docker-compose.yml > docker-compose.yml`

Then run with: `docker-compose up -d`

---

If you change your environmental variables and want them to be reflected in the image you need to recreate your volumes. You should first...   

1. `docker-compose stop mediawiki mariadb && docker-compose rm mediawiki mariadb && docker system prune`

3. Then...

    - If your volumes are mounted you can just delete the **mariadb_data** and **mediawiki_data** folders.

    - If your volumes are **NOT** mounted you would use `docker volume prune` to wipe to the unused volumes.

2. Finally, just re-run with: `docker-compose up -d`.

--- 

You also need a vars.env file with the below variables to store passwords. Make sure to include this in a .gitignore. 

```
MEDIAWIKI_WIKI_NAME=Wiki Name
MEDIAWIKI_USERNAME=Wiki User
MEDIAWIKI_PASSWORD=Wiki Password
MEDIAWIKI_DATABASE_PASSWORD=DB Pass
MARIADB_ROOT_PASSWORD=DB Root Pass
MARIADB_PASSWORD=DB Pass
SMTP_HOST=ssl://smtp.gmail.com
SMTP_HOST_ID=mydomain.com
SMTP_PORT=465
SMTP_USER=your_email@gmail.com
SMTP_PASSWORD=your_password
```