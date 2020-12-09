# Linux

## Add environment path

for `zsh`:

1. `vim ~/.zshrc`

   ```shell
   # >>> conda initialize >>>
   # !! Contents within this block are managed by 'conda init' !!
   __conda_setup="$('/Users/huangqiming/opt/miniconda3/bin/conda' 'shell.zsh' 'hook' 2> /dev/null)"
   if [ $? -eq 0 ]; then
       eval "$__conda_setup"
   else
       if [ -f "/Users/huangqiming/opt/miniconda3/etc/profile.d/conda.sh" ]; then
           . "/Users/huangqiming/opt/miniconda3/etc/profile.d/conda.sh"
       else
           export PATH="/Users/huangqiming/opt/miniconda3/bin:$PATH"
       fi
   fi
   unset __conda_setup
   # <<< conda initialize <<<
   
   
   # HomeBrew
   export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles
   export PATH="/usr/local/bin:$PATH"
   export PATH="/usr/local/sbin:$PATH"
   # HomeBrew END
   ```

2. in the end of the file add

   ```shell
   # Shell Script
   export MY_SCRIPTS=/Users/huangqiming/Desktop/Shell
   export PATH=$PATH:$MY_SCRIPTS
   # Shell Script END
   ```

## commands

### open

| Parameter | Usage                               | Example                                                      |
| --------- | ----------------------------------- | ------------------------------------------------------------ |
| -a        | open file with specific application | open -a /Applications/Typora.app/Contents/MacOS/Typora linux.md |

### . and source and .sh file

`.`:  execute the `.sh` file using current shell

`source`  is equal to `./`

### rm

| Parameter | Usage | Example |
| --------- | ----- | ------- |
|           |       |         |





# python

## tricks

reverse traversal

```python
a = [1,2,3,4,5]
for i in range(len(a)-1, -1, -1):
  print(a[i])
"""
5
4
3
2
1
"""
```



## numpy

np.delect(a, index)

```python
a = [1,2,3,4,5,6]
np.delect(a, 0) # [2,3,4,5,6]
np.delect(a, [2,3]) # [1,2,5,6]
```



# iTerm2

## short cut

| Command             | Usage                     |
| ------------------- | ------------------------- |
| command + t         | open new label            |
| command + w         | delete current label      |
| command + enter     | full screen model         |
| command + d         | vertially slice screen    |
| command + shift + d | horizontally slice screen |
| ^ + a               | switch to the line head   |
| ^ + e               | switch to the line end    |
| command + r         | clear screen              |
| ^ + u               | delete curren line        |
| shift + command + h | show all paste history    |

## tricks

save you paste history into disk:

`	Preferences -> General -> Magic -> Save copy/paste history to disk`

# Shell

## automatically git push

how to execute next command line only after the befor line had been finished

```shell
#!/bin/zsh
wait=`git add $1`
echo "Done git add"
out=`git commit -m 'update'`
echo "Done git commit"
result=`git push`
echo "Done git push"
```





