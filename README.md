# Postgresql installation in WSL Ubuntu 18.04
1. sudo apt-get update && sudo apt-get upgrade
2. sudo apt install postgresql postgresql-contrib postgis 
3. sudo service postgresql start
4. sudo -u postgres createuser simra
5. sudo -u postgres createdb simra
6. sudo -u postgres psql <br />
    psql=# alter user simra with encrypted password 'simra12345simra'; <br />
    psql=# grant all privileges on database simra to simra;  <br />
    psql=# alter role simra superuser;  <br />
    psql=# create extension postgis;  <br />
    psql=# \q  <br />
7. // copy db.sql.gz inside WSL
8. gzip -d db.sql.gz 
9. sudo -u postgres psql simra < ./db.sql
