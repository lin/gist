```
sudo vi /etc/nginx/sites-available/default
```

Edit as in file 12 on this page.

Then start the nginx to test result.

```
# make sure you are at /var/www/[app]
mkdir log
rake db:create
rake db:migrate
rake db:seed
unicorn_rails -c config/unicorn.rb -D
sudo service nginx restart
```