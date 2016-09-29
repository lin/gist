Create your app folder.

```
sudo mkdir -p /var/www
sudo chown -R ubuntu:ubuntu /var/www
sudo chmod -R g+rw /var/www
cd /var/www
```

Install your app

```
git clone https://github.com/[username]/[app].git
cd [app]
bundle install
```