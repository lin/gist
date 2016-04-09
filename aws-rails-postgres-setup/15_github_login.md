This step will help you with github settings, so that you don't need to enter your github account and password everytime you make changes.

Please [reference this page for details.](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
$ eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_rsa
```

```
$ pbcopy < ~/.ssh/id_rsa.pub
# copy the content to clipboard
```

```
ssh -T git@github.com
git config --global credential.helper cache
git config --global credential.helper 'cache --timeout=3600'
```