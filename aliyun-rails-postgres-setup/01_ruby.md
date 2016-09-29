*Last update, 04-08-2016*

```
sudo apt-get update
```

#### RVM

```
sudo apt-get install curl
# visit https://rvm.io/ for detais, currently it works by following commands.
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
\curl -sSL https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
# [[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"
rvm requirements
rvm -v
```

#### Ruby

```
rvm install ruby
rvm use ruby --default
rvm rubygems current
ruby -v
```
