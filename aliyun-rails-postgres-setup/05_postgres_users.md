
Create user (role) `postgres` and assign a password to it.

```
sudo -u postgres psql postgres
\password postgres
\q # to quit
```

Since it's connected locally only, we can use peer authentication.

```
# create user (role) ubuntu
sudo -u postgres createuser --superuser $USER

# set password for user ubuntu
sudo -u postgres psql
\password $USER
\q

# create a database named ubuntu
sudo -u postgres createdb $USER
```
===========================

#### Additional Information

If you want to change it to `md5` authentication, you need to change `pg_hba.conf` file.

```
sudo vi /etc/postgresql/9.3/main/pg_hba.conf # local all [username] md5
sudo /etc/init.d/postgresql restart
```
