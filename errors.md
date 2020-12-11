# git 

```shell
fatal: unable to access 'https://github.com/Thomaszz4/Shell.git/': Couldn't connect to server
```

SOLOTION: change `https` to `git`  but can not push this repo

```shell
You can't push to git://github.com/Thomaszz4/Shell.git
Use https://github.com/Thomaszz4/Shell.git
```

SOLUTION: using `git clone https://github.com/Thomaszz4/Shell.git`

```shell
error: failed to push some refs to 'https://github.com/xxxx.git'
```

SOLOTION: the remote repo changed, `git pull` first then `git push` again

# zsh

```shell
Insecure completion-dependent directories detected
```

SOLUTION: that is because some of the file lack of authority, `chmod 775 xx/xx`





