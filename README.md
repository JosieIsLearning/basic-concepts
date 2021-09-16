# linux基础了解

![image-20210806083731628](LinuxCMD.assets/image-20210806083731628.png)

分区：把大硬盘分为小的逻辑分区

格式化：写入文件系统

分区设备文件名：给每个分区定义设备文件名

挂载：给每个分区分配挂载点（空目录）

# 命令行用语 

> command[options] [arguments]
>
> command:告诉LINUX做什么
>
> options:说明命令运行的方式，以-开始
>
> arguments: 说明命令影响的是什么

+ 为什么用命令行？
  + 命令比图形操作稳定
  + 远程操作服务器时图形操作会使网络的流量大增

## 开关机命令

重启系统`reboot init 6`

关闭系统`poweroff init 0`

关机`shutdown`

10分钟后关机`shutdown -h 10`

现在立刻重启`shutdown -r now`

10分钟后重启`shutdown -r+10`  

### 内核的引导

### 运行init

init 进程是系统所有进程的起点，你可以把它比拟成系统所有进程的老祖宗，没有这个进程，系统中任何进程都不会启动。

init 程序首先是需要读取配置文件 /etc/inittab。

Linux系统有7个运行级别(runlevel)：

- 运行级别0：系统停机状态，系统默认运行级别不能设为0，否则不能正常启动
- 运行级别1：单用户工作状态，root权限，用于系统维护，禁止远程登陆
- 运行级别2：多用户状态(没有NFS)
- 运行级别3：完全的多用户状态(有NFS)，登陆后进入控制台命令行模式
- 运行级别4：系统未使用，保留
- 运行级别5：X11控制台，登陆后进入图形GUI模式
- 运行级别6：系统正常关闭并重启，默认运行级别不能设为6，否则不能正常启动

### 系统初始化

### 建立终端

### 用户登录系统

退出LINUX操作系统：action->log out /`init 0`

登录：`Josie login:`

验证当前使用的虚拟终端：`tty`

退出Linux系统：`exit`

返回图形化终端：`ctrl+alt+F7`

## ls命令

list 的缩写，通过 ls 命令不仅可以查看 linux 文件夹包含的文件，而且可以查看文件权限(包括目录、文件夹、文件权限)查看目录信息等等

```linux
ls -a 列出目录所有文件，包含以.开始的隐藏文件
ls -A 列出除.及..的其它文件
ls -r 反序排列
ls -t 以文件修改时间排序
ls -S 以文件大小排序
ls -h 以易读大小显示
ls -l 除了文件名之外，还将文件的权限、所有者、文件大小等信息详细列出来
```





打开文件夹`cd`

`sudo apt-`





# To Begin
## A sense of location
1. find a launcher: Ctrl+Alt+T
2. close it:`Ctrl-D`
3. prompt(be ready to accept a command):`pwd`
	 +  pwd = print working directory
	 + working directory: the shell has a notion of a default location in which any file operations will take place
4. Change directory: `cd`
5. go up to the parent directory:
	```
	cd .. 
	pwd``` 
6. get back to your home directory:
	 ```
	cd
	pwd
	```
7. move up through multiple levels of parent directories:
	```
	cd ../..
	pwd
	```
## Create Folders and Files
1. folder:`mkdir /tmp/tutorial`
2. sub-directories: `mkdir dir1 dir2 dir3`
3. create parent directories:`mkdir -p dir4/dir5/dir6`
4. they mean the same thing:
	```
	mkdir --parents --verbose dir4/dir5
	mkdir -p --verbose dir4/dir5
	mkdir -p -v dir4/dir5
	mkdir -pv dir4/dir5
	```
5. folders with spaces: `makedir "folder 1"`
##  Creating files using redirection
1. capture the output of that command as a text file: `ls > output.txt`
2. look at its content: `cat output.txt`
3. print its argument back out again: `echo "This is a test"
4. create small files:
	```
	echo "This is a test" > test_1.txt
	echo "This is a second test" > test_2.txt
	echo "This is a third test" > test_3.txt
	ls
	```
5. concatenate - to link together: `cat test_1.txt test_2.txt test_3.txt`
	(f you pass more than one filename to `cat` it will output each of them, one after the other, as a single block of text)
6. ==?== “any single character” within the file name
	==*== “zero or more characters”
7. join all our files together into a single new file:
	```
	cat t* > combined.txt
	cat combined.txt
	```
8. append a line:
	```
	cat t* >> combined.txt
	echo "I've appended a line!" >> combined.txt
	cat combined.txt
	```
9. view the text: `less combined.txt`
10. quit and return to command line: `q`
## Moving and manipulating files
1. move sth into our directory
	- `mv conbined.txt dir1`
2. copy files:`cp combined.txt backup_conbined.txt`
3. rename the file:`mv backup_combined.txt combined_backup.txt`
## Deleting files and folders
1. remove files: `rm combined.txt`
2. remove directory: `rmdir folder_*` 
	- only delete <u>empty</u> files
3. remove everything: `rmdir -p`
4. remove anything in it:`rm -rm folder_6`
5. confirm the deletion of each file: `rm -i`, stop the preaion entirely: Ctrl-C.
6. ==To Note==:`rm t*` means “delete all the files starting with _**t**_”, whereas `rm t *` means “delete the file _**t**_ as well as any file whose name consists of zero or more characters.
## A bit of plumbing
1. count line: `wc -l *.txt`
2. to know how many files and folders are in your home directory, and then tidy up after yourself:
	```
	ls ~ > file_list.txt
	wc -l file.list.txt
	rm file_list.txt
	```
	- equals to: `ls ~ | wc -l`
	- see how many items are in the directory:`ls /etc | wc -l`
	- list them in a single screen:`la /etc | less`
	- given that it was created by concatenating the same files multiple times, I wonder how many unique lines there are:`cat combined.txt | uniq | wc -l`
3. looking for a manual: `man uniq`
4. sort the contents of the file alphabetically:`sort combined,txt | less`
## The command line and the superuser
1. Do not use root as your main ,or only, account.
2. change to another user:`su`
3. return to their user-level account:`logout` Ctrl-D
4. request superuser rights on a per-command basis:`sudo`
	switch user and do this command.
5. install new software:`sudo apt install free`
## Hidden Folders
- starting with a dot to make it disappear:
	```
	cd /tmp/tutorial
	ls
	mv combined.txt .combined.txt
	ls
	```
	```
	cat .combined.txt
	mkdir .hidden
	mv .combined.txt .hidden
	less .hidden/.combined.txt
	```
- to show all: `-a`
	```
	ls -a
	ls -a .hidden
	```
