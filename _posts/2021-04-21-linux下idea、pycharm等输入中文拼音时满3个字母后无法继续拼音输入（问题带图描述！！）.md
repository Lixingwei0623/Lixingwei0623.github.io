@[TOC](linux下idea、pycharm等输入中文拼音时满3个字母后无法继续拼音输入)

# 问题描述：idea输入中文，没输入几个拼音就好像自动回车，有时得到几个字母，然后就不能输入拼音了。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210421220812103.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/2021042122085224.png)
遇到这个情况就导致输入中文特别困难，可以采取：
## 修改idea.sh和pycharm.sh文件来改变语言输入设置。
## 找到自己idea或pycharm安装的地方，/bin/idea.sh
![bin目录](https://img-blog.csdnimg.cn/20210421221531462.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)

## 编辑idea.sh文件，在最后新增以下几行代码：
```
export XIM="ibus"
export XIM_PROGRAM="ibus"
export XMODIFIERS="@im=ibus"
export GTK_IM_MODULE="ibus"
export QT_IM_MODULE="ibus"
```
此处每行代码的ibus要根据自己系统的输入法来设置，有的是fcitx，可以在设置里看，点击下图的管理已安装语言出现语言支持对话框，键盘输入法系统：IBus
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210421222350236.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)
如果你是fcitx的话，请在idea.sh里加入：
```
export XIM="fcitx"
export XIM_PROGRAM="fcitx"
export XMODIFIERS="@im=fcitx"
export GTK_IM_MODULE="fcitx"
export QT_IM_MODULE="fcitx"
```
## 然后``source /etc/profile``更新一下配置文件，重启idea就可以了输入中文了
![在这里插入图片描述](https://img-blog.csdnimg.cn/202104212219562.png)

# Pycharm同理更改pycharm.sh文件

# 注：这种情况一般是正常的配置没有被加载进来，如果是使用环境变量来通过命令行idea.sh的方式进入的话，大概率会有问题。
可以先从idea的bin目录下，./idea来运行idea，然后进入后发现是可以正常输入中文的，然后在Tools->Create Desktop Entry来创建快捷方式，以后通过快捷方式进入就不会有问题了。
