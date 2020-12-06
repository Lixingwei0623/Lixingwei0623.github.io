@[TOC](Linux系统（ubuntu）常用命令)
本文所有命令均在ubuntu上正常操作，命令只包括一些常用的快速上手的命令，适合初学者查看。
# 一、文件和目录操作

## 1.cd /home	进入 /home 目录
	cd /home

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130112524395.png)

## 2.cd ..		返回当前目录的上一级目录
	cd ..
	
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113146381.png)

## 3.cd ../..		返回当前目录的上两级

	cd ../..

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113154386.png)

## 4.cd	进入当前用户的主目录
	cd

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020113011321189.png)

## 5.cd ~username	进入username用户的主目录
	cd ~username

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113224498.png)

## 6.cd -	返回上次所在的目录
	cd -
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113235506.png)

## 7.pwd		显示当前工作路径
	pwd

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113242650.png)

## 8.ls	显示当前目录的文件
	ls

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020113011325255.png)

## 9.ls -F		显示当前目录的文件
	ls -F

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113301761.png)

## 10.ls -l		显示当前目录下的所有文件及详细信息
	ls -l

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113311147.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)

## 11.ls -a	将隐藏文件一同显示出来
	ls -a

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020113011333474.png)

## 12.mkdir dir1		新建一个dir1文件夹
	mkdir dir1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113345904.png)

## 13.mkdir dir1 dir2		新建两个文件夹，也可以新建3,4...个
	mkdir dir1 dir2

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113356733.png)

## 14.rmdir dir1		删除dir1文件夹
	rmdir dir1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113405112.png)

## 15.rm -rf dir1		删除dir1文件夹及其里面的内容
	rm -rf dir1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113418664.png)

## 16.mv dir1 new_dir		将dir1移动到new_dir处，并重命名为new_dir
	mv dir1 new_dir

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113426562.png)

## 17.touch file.txt			在当前目录新建一个file.txt文件
	touch file.txt

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113433271.png)

## 18.cp file new_file	将file文件复制，然后另存为new_file
	cp file new_file

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113442156.png)

## 19.cp -r dir1 new_dir2		将dir1及其子目录复制并另存为new_dir2
		cp -r dir1 new_dir2

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113453758.png)

## 20.ln -s file1 link1 	创建一个指向文件或文件夹(目录)file1的软链接link1，相当于快捷方式
	ln -s file1 link1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113505448.png)

## 21.ln file1 link1		创建一个硬链接link1指向file1，注意：不允许将硬链接指向目录
	ln file1 link1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113512398.png)

# 二、用户和群组操作

## 1.addgroup group_name		创建一个group_name用户组，注意：只有root用户可以创建
	addgroup group_name

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113529289.png)![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113536560.png)

## 2.delgroup group_name		删除名为group_name的用户组
	delgroup group_name

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113553956.png)

## 3.groupadd group_name和groupdel group_name	效果与1，2大致相同
	groupadd group_name
	groupdel group_name

![在这里插入图片描述](https://img-blog.csdnimg.cn/202011301136050.png)

## 4.useradd -c "Comments" -g root -d /home/user1 username		创建一个用户名为username，备注信息为Comments，群组为root，登入目录为/home/user1
	useradd -c "Comments" -g root -d /home/user1 username

## 5.useradd username		创建一个用户名为username的用户
	useradd username

## 6.useradd -r userdir username	创建一个用户名为username的用户，登入目录为userdir
	useradd -r userdir username

## 7.userdel -r userdir username		删除一个用户名为username的用户，并删除其登入目录userdir
	userdel -r userdir username

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020113011362390.png)

## 8.usermod -c “Comments” -g group -d /home/dir username		修改username用户的备注为Comments，群组为group，登入目录为/home/dir
	usermod -c “Comments” -g group -d /home/dir username

## 9.passwd	修改当前用户密码
	passwd

## 10.passwd user1	修改user1用户的秘密
	passwd user1

## 11.chage -E 2020-12-20 user1		设置用户user1用户密码失效日期
	chage -E 2020-12-20 user1

## 12.su	切换root用户，sudo也是一样
	su
	sudo

## 13.sudo -i	从当前管理员用户切换到root用户，适合忘记root密码的时候操作
	sudo -i

## 14.exit	退出当前用户
	exit

# 三、文件的权限操作

## 1.ls -lh	显示所有文件以及其权限
	ls -lh

注：d开头代表文件夹，l开头代表软链接，之后的每一组rwx，分别对应文件所有者、文件所有者群组用户、普通用户的读写执行权限，-代表无该权限，然后第一个用户名是文件所有者，第二个是群组。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113701288.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)

## 2.chown username file	将file文件的所有者改为username用户
	chown username file

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113729214.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)


## 3.chomd ugo+rwx dir1		设置目录dir1的所有人(u)、群组(g)以及其他人(o)以读（r ）、写(w)和执行(x)的权限 
	chomd u+x dir1	//给所有者(u)以目录dir1的执行(x)权限
	chomd g+w dir1
	chomd o+r dir1

## 4.chown user1:group1 file1  改变文件file1的所有人和群组属性为user1和group1
	chown user1:group1 file1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113740501.png)

# 四、文件搜索

## 1.find / -name file1		/代表根目录，-name代表按文件名搜索，搜索到名字为file1的文件或目录会显示它的路径
	find / -name file1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113755828.png)

## 2.find / -user user1		搜索所有者为user1的文件或目录，显示它们的路径
	find / -user user1

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113804128.png)

## 3.find /home -name \*.txt	在/home路径下搜索以.txt结尾的文件
	find /home -name \*.txt

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201130113813807.png)

# 五、查看或编辑文件内容

## 1.cat file1	从第一个字节开始正向查看文件file1的内容
	cat file1

## 2.tac file1	从最后一行开始反向查看文件file1的内容
	tac file1

## 3.head -2 file1	查看文件file1的前两行
	head -2 file1

## 4.tail -2 file1		查看文件file1的最后两行
	tail -2 file1

## 5.vim file1		使用vim来编辑文件file1，进入后按i开始编辑，编辑完按esc，然后输入：wq可以保存并退出
	vim file1

## 6.gedit file1	使用gedit来编辑文件file1，gedit是ubuntu默认的文本编辑器
	gedit file1
