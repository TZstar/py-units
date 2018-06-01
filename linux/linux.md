# linux常用操作

## 一、基础操作

### 1.创建共享文件
	（windows-ip:10.36.137.221）

	文件共享(NFS)
	安装nfs服务: sudo apt install nfs-kernel-server -y
	安装nfs客户端: sudo apt install nfs-common -y
	
	sudo mount 10.36.137.69:/home/hadoop/tmp  /home/用户


### 2. 复制文件
1. `cp`:本地拷贝文件
2. `scp`:远程拷贝文件命令
	- 远程文件 => 本地目录
		`scp root@10.10.10.10:/opt/soft/nginx-0.5.38.tar.gz /opt/soft/`
	- 远程目录 => 本地目录
		`scp -r root@10.10.10.10:/opt/soft/mongodb /opt/soft/`
	- 本地文件 => 远程目录
		`scp /opt/soft/nginx-0.5.38.tar.gz root@10.10.10.10:/opt/soft/scptest`
	- 本地目录 => 远程目录
		`scp -r /opt/soft/mongodb root@10.10.10.10:/opt/soft/scptest`
3. `rcp`:
4. `ftp`:
5. `ncftp`:

### 3. 批量kill文件
1. `ps -ef|grep python|grep -v grep|cut -c 9-15|xargs kill -9`
	* `ps -ef`: Red Hat 里查看所有进程的命令。这时检索出的进程将作为下一条命令“grep LOCAL=NO”的输入。 
	* `grep python`: 所有含有 python 关键字的进程。
	* `grep -v grep`: 在列出的进程中去除含有关键字“grep”的进程。
	* `cut -c 9-15`: 截取输入行的第9个字符到第15个字符，而这正好是进程号PID。
	* `xargs kill -9`: xargs命令是用来把前面命令的输出结果（PID）作为“kill -9”命令的参数，并执行该令。


### 4. 查看历史记录
1. 常用命令
	`history N`：显示最近的N条命令，例如history 5 
	`history -d N`：删除第N条命令，这个N就是前面的编号，例如history -d 990 
	`history -c`：清空命令历史。但是不会清除 `.bash_profile` 文件中的记录。
	`history -a`：将当前会话中的命令历史写入指定文件 
	`echo $HISTFILE`：使用此命令查看环境变量
2. 查看带【时间，用户】的日志记录
	- 在~/.bashrc文件中添加如下行
		```
		HISTTIMEFORMAT="%Y-%m-%d %H:%M:%S:`whoami`:  "  # 必须放置到 export 之前
		ISTFILESIZE=2000     # 设置保存历史命令的文件大小
        HISTSIZE=2000       # 保存历史命令条数
 		export HISTTIMEFORMAT
		
		```
	- 然后执行 `source  ~/.bashrc` 生效即可；
	