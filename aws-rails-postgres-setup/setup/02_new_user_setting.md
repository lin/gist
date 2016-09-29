
```
su ubuntu # change user from root to ubuntu
sudo mkdir /home/ubuntu
sudo chown ubuntu -R /home/ubuntu
cd ~
```

======================
======================

If necessary, change shell [more info at here](http://superuser.com/questions/68397/why-does-my-linux-prompt-show-a-instead-of-the-login-name-and-path)
```
echo $SHELL
which bash
sudo chsh -s /bin/bash ubuntu # as root user
#replacing /bin/bash with whatever the appropriate path for your shell of choice is.
```
