Make unicorn script executable.

```
sudo chmod +x config/unicorn_init.sh
```

Make it a service.
```
sudo cp config/unicorn_init.sh /etc/init.d/unicorn
```

===========================

#### Additional Information

You can start / restart / stop server by

```
$ sudo service unicorn start/restart/stop
```