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
# :x! to quit
```
