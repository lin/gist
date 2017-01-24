[Based on this article.](http://www.thegeekstuff.com/2009/01/how-to-backup-and-restore-postgres-database-using-pg_dump-and-psql/)

1, backup database using:

```
# for development
pg_dump -U ubuntu app_development -f ~/Downloads/app.sql

# for production
pg_dump -U ubuntu app_production -f ~/backups/app.sql
```

2, upload to the server.

```
scp -i ~/.ssh/app.pem ~/Downloads/app.sql ubuntu@[ip]:/var/www/db
```

3, drop db and create db

```
dropdb 'app_production'
createbd 'app_production'
```

4, restore the db

```
psql -U ubuntu -d app_production -f app.sql
```
