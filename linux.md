# Linux


## shell
* update


Record commands
* quick open file with designated application: `open` 

* iterm2
	* creat new windows: `command + t` or `command + n`

* ssh
	```shell
	The ECDSA host key for website.thomaszz4.xyz has changed,
	and the key for the corresponding IP address 124.71.47.204
	is unchanged. This could either mean that
	DNS SPOOFING is happening or the IP address for the host
	and its host key have changed at the same time.
	Offending key for IP in /Users/huangqiming/.ssh/known_hosts:49
	```
	* this happen when I used ssh by sending domain name resolution, for example, before, I used to bind my IP like `123.123.123.123` to `website.thomaszz4.xyz` and now I changed my IP to `222.222.222.222`. So I have to clear the previous ssh cache data
	* SOLUTION: In the terminal, `ssh-keygen -R website.thomaszz4.xyz` to clear your old cache data

* git
	* when used `git clone https://github.com/Thomaszz4/Thomaszz4.github.io.git`, it stoped at:
	```shell
	Unpacking objects:  36% (24/66)
	```
	* change `https` to `git`, that is `git clone git://github.com/Thomaszz4/Thomaszz4.github.io.git`
	* if you using `git clone git://github.com/Thomaszz4/Thomaszz4.github.io.git`, when you `git push` may met some problems
	* new branch: `git branch new_branch`, push the current branch and set the remote as upstream: `git push --set-upstream origin test_branch`

* jupyter
	* set up a remote connect
	* `jupyter notebook --generate-config` to generate config file and it will generate at: `/Users/huangqiming/.jupyter/jupyter_notebook_config.py`
	* `jupyter notebook password` to set your password, the password will store at `/Users/huangqiming/.jupyter/jupyter_notebook_config.json`
	* check your password: `sudo vim /Users/huangqiming/.jupyter/jupyter_notebook_config.json` you will get:
	```shell
	{
	  "NotebookApp": {
	    "password": "sha1:c06b604b301a:845bd85fbe4c887dc0ac10587ce240bff9bc0bbd"
	  }
	}
	```
	* the `sha1:c06b604b301a:845bd85fbe4c887dc0ac10587ce240bff9bc0bbd` is your password
	* then, change config `sudo vim /Users/huangqiming/.jupyter/jupyter_notebook_config.py`, find or add:
	```shell
	c.NotebookApp.ip = '*'
	c.NotebookApp.open_browser = False
	c.NotebookApp.password = 'sha1:e97b082bfe17:e4ba1fdc2f85d110f4e3d1acfd35933401f4fb93'
	c.NotebookApp.port = 4567
	```
	* `'*'` donates allow all ip to access, add your password got from `jupyter_notebook_config.json` , `4567` specific the port, pay attention, make sure you open the `4567` port.
	* run, `jupyter notebook`
	* check kernel list : `jupyter kernelspec list`
	* install c++ kernel: `conda install xeus-cling -c conda-forge`

* things about ports in linux
	* Using ufw (Uncomplicated Firewall)
		* check state of ports: `ufw status`
		* open port: `ufw open 1234` and `ufw reload`

* vim
	* vim has three modes, `Insert Mode`, `Visual Mode`, `Command Mode`
	* command reference:
		* vertical spilt: in the command mode `:vsplit test1.txt` will split the screen
		* copy: `y`
		* cut a line: `dd`, you can then paste
		* paste: `p`
		* `h` left, `l` right, `j` down, `k` up
		* `0` the start of this line, `$` the end of this line
		* `gg` go to the first line of the file, `G` go to the end of the file, `no of line G` to the the specific line (for example `7 G` go to 7 line)
		* `x` delete current word, `dw` delete all the words after current in this line
		* `u` undo, `<ctrl> r` cancel undo
		* execute the external commands: `:!shell ls` for instance
	* search operations
		* in the command mode, `/linux` to search linux, then use `n` to switch to the next one and `b` to the below one.
		* if you are in the bottom of the file, you can use `?linux`
	* customize search
		* highlight search: in the command mode, `:set hlsearch`
		* search ignoring case-sensitive: `:set ignorecase`

* sftp
	* easily used for transfer files to the remote service
	* `sftp root@192.168.1.1` to connect
	* `ls` list the file on the remote service, `lls` list the file on the local, lls (local ls)

* tmux 
	* `tmux new -s <session-name>`















