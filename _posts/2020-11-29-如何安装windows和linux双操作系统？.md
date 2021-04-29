@[TOC](如何安装windows和linux双操作系统？)

目标：在已经安装了windows操作系统的情况下，安装一个ubuntu桌面版，以便每次在开机时可以选择要使用的操作系统。
# 一、win压缩卷：

这一步是从磁盘中分割空间供linux系统使用。

## 1.右键此电脑，选择管理，选择磁盘管理。

![进入磁盘管理](https://img-blog.csdnimg.cn/20201129143930349.png)
![磁盘管理界面](https://img-blog.csdnimg.cn/20201129144019117.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)
## 2.挑选一个磁盘然后右击选择压缩卷，空间大小自己确定。
注意：至少10G以上。
![压缩卷](https://img-blog.csdnimg.cn/20201129144148283.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129144809801.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)

# 二、下载复刻工具和iso光盘映像文件：
我们需要下载的资源包如图：
ubuntu-18.04.5-desktop-amd64.iso
win32diskimager-1.0.0-install.exe
![](https://img-blog.csdnimg.cn/20201129144737237.png)

 

## 1.把它们都下载好，然后点击运行刻录工具。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145257568.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)


 

## 2.所有选项都默认，然后点击next就完事。然后到这个界面。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145339824.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)


 

## 3.选择好映像文件和U盘，开始写入。（注意写入后，U盘所有文件将被覆盖。）

## 4.写入完成。

## 5.将电脑关机。

# 三、开始安装linux系统：

## 1.开机时，持续摁自己电脑机型对应的键来进入BIOS，我的是esc键。
参考下图可以知道自己该摁哪个键。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145541738.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)

 

## 2.选择U盘驱动

## 3.点击桌面上Install Ubnmtu 18.04.5 LTS，出现欢迎界面，可以自己选语言。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145659915.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)

 
## 4.键盘输入可以如图选：(语言按自己习惯选)
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145720419.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)


## 5.选正常安装：

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145759720.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)


## 6.安装类型：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145816594.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)

 
图有点不清楚，不过选第一个，让两个系统共存，就不用后面的分区了。

## 7.安装，几分钟后出现如下界面：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201129145852911.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)


 

# 四、问题：wifi无法使用，已解决。

“未发现wifi适配器”。
需要联网下载更新驱动，可以通过手机USB共享网络进行下载，可参考博客：https://my.oschina.net/aomojan/blog/3010779



