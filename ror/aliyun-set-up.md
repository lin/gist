Based on [this article](https://ruby-china.org/topics/17553).

Aliyun - Ubuntu - Rails - Mongoid - Nginx - Unicorn application setup workflow.

Ubuntu 12.04 64位 - Mac OS X 10.11.1

ruby 2.0.0p648 - rvm 1.27.0 - rails 4.2.6

A mongoid version: [gist maybe blocked in China](https://gist.github.com/linyingkui/b66708fe366e88d3b9b3)

1, install curl

```
$ apt-get update
$ apt-get install curl
```

2, install rvm, visit rvm.io
```
$ gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
$ \curl -L https://get.rvm.io | bash -s stable
$ echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm"' >>~/.bashrc
$ source ~/.bashrc
$ apt-get ruby-rvm
$ rvm -v # check
```

3, install rvm requirements

```
$ rvm requirements
$ rvm pkg install readline
$ rvm pkg install openssl
```

4, install ruby and gem
```
$ rvm install ruby
$ rvm use ruby --default
$ rvm rubygems current

$ ruby -v
$ gem -v

$ gem source -r https://rubygems.org/
$ gem source -a http://mirrors.aliyun.com/rubygems/
$ gem sources -l
```

5, install rails

```
gem install rails
rails -v
```

```
apt-get install libsqlite3-dev
gem install sqlite3-ruby
apt-get install nodejs npm
gem install railties
```

```
mkdir ~/test
cd ~/test
rails new app
cd app
vi Gemfile # source 'http://mirrors.aliyun.com/rubygems/'
rails g scaffold User name:string
rake db:migrate
bundle exec rails server -b 0.0.0.0
```

6, install sql (mysql or postgresql)

```
apt-get install postgresql postgresql-client libpq-dev
```

7, install git

```
sudo apt-get install git
git config --global user.name "NewUser"
git config --global user.email newuser@example.com
```

8, install your app
```
git clone https://github.com/username/app.git
cd app
rm Gemfile.lock
bundle install # source 'http://mirrors.aliyun.com/rubygems/'
rake db:create
rake db:migrate
```
