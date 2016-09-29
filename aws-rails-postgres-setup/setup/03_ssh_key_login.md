Based on [this article](http://www.cnblogs.com/bashenandi/p/linux-aliyun-ecs-ssh.html)

```
mkdir ~/.ssh
# sudo chown ubuntu .ssh # grant permission if need
ssh-keygen -t rsa
```

You will get two files, which are `id_rsa` and `id_rsa.pub`

The second is the public key. The first is the private key.

rename the `id_rsa.pub` to sshd default public keys name
```
mv ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys
chmod 400 ~/.ssh/authorized_keys
```

========================================
===============NOT SEVER================
========================================

Copy the content in `id_rsa`, store in a `.pem` file in your own computer, like`~/.ssh/xuyu.pem`

```
vi ~/.ssh/id_rsa
chmod 400 ~/.ssh/xuyu.pem # grant permission if need
```

========================================
===============NOT SEVER END============
========================================

Then you can delete the server side version of id_rsa
```
rm –rf ~/.ssh/id_rsa
```

Change sshd settings
```
sudo vi /etc/ssh/sshd_config
```
Uncomment following
```
AuthorizedKeysFile      %h/.ssh/authorized_keys
```

```
sudo service ssh restart
```

You can connect to server by
```
ssh ubuntu@ip -i ~/.ssh/xuyu.pem
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

You can also config a shortcut in `~/.ssh/config`

```
Host xuyu
	HostName [ip]
	User ubuntu
	IdentityFile ~/.ssh/xuyu.pem
```

```
ssh xuyu
```

=================

You can also change more sshd settings, like
```
#仅使用SSH2协议
Protocol 2

#修改密钥生成强度
ServerKeyBits 1024

#禁止root账户通过ssh登录
PermitRootLogin no

#禁止使用常规的用户名密码方式登录，此项慎用
#在没有生成好Key，并且成功使用之前，不要设置为no
PasswordAuthentication no

#禁止空密码登录
PermitEmptyPasswords no
```
