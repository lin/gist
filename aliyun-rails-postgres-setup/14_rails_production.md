Add secret key for devise and production environment
```
rake secret
sudo vi ~/.bash_profile
```

Add this line
```
export SECRET_KEY_BASE='secret'
```

```
. ~/.bash_profile
echo $SECRET_KEY_BASE
```

Remember to migrate database again for production database.
```
RAILS_ENV=production rake db:create
RAILS_ENV=production rake db:migrate
RAILS_ENV=production rake db:seed
```

Reboot the instance to load the new env variables. Then start the unicorn and nginx.

```
sudo service unicorn start
sudo service nginx start
```

===========================

#### Additional Information

Multiple sites

```
sudo ln -s /etc/nginx/sites-available/cataluv.conf /etc/nginx/sites-enabled/cataluv.conf
```