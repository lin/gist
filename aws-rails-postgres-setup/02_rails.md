#### Rails
```
gem install rails
rails -v
```

```
sudo apt-get install libsqlite3-dev
gem install sqlite3
sudo apt-get install nodejs npm
gem install railties
```

```
mkdir ~/test
cd ~/test
rails new app
cd app
rails g scaffold User name:string
rake db:migrate
bundle exec rails server -b 0.0.0.0
```

Visit yourwebsite.com:3000 to see result (as shown in the following image). **Remeber you have to open the port 3000 for outbound in your Security Groups to see the result.**

![rails success](http://i.imgur.com/RVV3zMP.png?1)

Also, you can check yourwebsite.com:3000/users to test the database.

`control + c` to terminate the WEBrick server.