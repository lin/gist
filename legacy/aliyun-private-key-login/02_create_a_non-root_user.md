Make a new user.

```
useradd ubuntu
passwd ubuntu
```

Grant privilege:
```
sudo vim /etc/sudoers
```

Change lines as:
```
# User privilege specification
root    ALL=(ALL:ALL) ALL
ubuntu  ALL=(ALL:ALL) ALL
```

Change shell [more info at here](http://superuser.com/questions/68397/why-does-my-linux-prompt-show-a-instead-of-the-login-name-and-path)
```
echo $SHELL
which bash
chsh -s /bin/bash
#replacing /bin/bash with whatever the appropriate path for your shell of choice is.
```
