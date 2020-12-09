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
|           |                                     |                                                              |
|           |                                     |                                                              |
|           |                                     |                                                              |
|           |                                     |                                                              |
|           |                                     |                                                              |
|           |                                     |                                                              |
|           |                                     |                                                              |
|           |                                     |                                                              |

### . and source and .sh file

`.`:  execute the `.sh` file using current shell

`source`  is equal to `./`

### rm

| Parameter | Usage | Example |
| --------- | ----- | ------- |
|           |       |         |





# python



