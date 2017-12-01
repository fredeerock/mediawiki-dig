# Get Started

1. Grab the docker-compose file with:  
`curl -sSL https://raw.githubusercontent.com/fredeerock/mediawiki-dig/master/docker-compose.yml > docker-compose.yml`

2. Then run with: `docker-compose up -d`

3. Update all the passwords in **docker-compose** under the **environment** section.

---

If you change your environmental variables and want them to be reflected in the image you need to recreate your volumes. You should first...   

1. `docker-compose stop mediawiki mariadb`

3. Then...

    - If your volumes are mounted you can just delete the **mariadb_data** and **mediawiki_data** folders.

    - If your volumes are **NOT** mounted you would use `docker-compose rm mediawiki mariadb && docker volume prune` to wipe to the unused volumes.

2. Start up again with: `docker-compose up -d`.

--- 

