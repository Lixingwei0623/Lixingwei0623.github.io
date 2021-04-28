@[TOC](Linux下的C语言入门（以ubuntu为例）)

# 一、编辑器vi(vim)
vi是最常用的文本编辑器，我们可以使用它来编写C语言代码。

	vi hello.c	//编辑一个名为hello.c的文件


进入vi编辑器后，有两种模式：命令模式、插入模式。
一进来就时命令模式，输入i在当前光标处开始插入字符，可以用上下左右箭头控制输入。摁``esc``键可回到命令模式，下面介绍命令模式下几种常用的命令：

	3 dd	//将光标所在行往下共3行代码剪切
	3 yy	//将光标所在行往下共3行代码复制
	p	//粘贴
	:set nu	//显示行号
	:sp filename	//新建一个文件并打开编辑窗口
	:wq	//保存并退出
	:q	//退出
	:q!	//强制退出

# 二、编译命令
	//将hello.c编译，编译输出文件名为hello.out
	gcc hello.c -o hello.out	

![编译](https://img-blog.csdnimg.cn/20201217110149954.png)
编译完成后，就可以运行hello.out文件：

	./hello.out

![运行](https://img-blog.csdnimg.cn/20201217110411114.png)
# 三、使用gdb调试代码
注意要使用gdb来调试代码，在我们编译的时候，编译命令要多加一个参数``-g``，格式如下：

	gcc hello.c -o hello.out -g

然后就可以对程序调试了：

	gdb hello.out

然后进入到调试环境（gdb）,我们下面介绍一些基本的调试命令：

	l	//显示源代码
	start	//开始调试，可以运行到下一个断点
	break 6	//在第六行添加一个断点
	break max	//在函数max的起始位置添加断点
	info break	//显示所有断点
	delete numofBreak	//删除编号为numofBreak的断点
	n	//执行一行语句，注意不进入函数内部
	s	//执行一行语句，遇到函数会进入函数内部
	finish	//执行完当前函数
	p a	//查看变量a的值
	p &a	//查看变量a的地址
	bt	//查看函数栈，可以看到函数序号
	f 1	//切换到序号为的1的函数
	q	//退出gdb调试

# 四、多文件编译及makefile的使用
命令格式：

	gcc hello1.c hello2.c hello12.c -o hello.out -g

在hello1.c,hello2.c,hello12.c里的函数可以相互调用，当我们的源文件有很多很多时，每次都手动输入这些命令麻烦且容易出错，因此我们要使用make工具来管理这些编译命令，以达到快捷编译的效果。
使用方式：新建一个makefile文件，然后在里面编写内容：

	/*格式：
	 *	outputfilename:file1 file2 file3
	 *	|<- tab->| gcc file1 file2 file3 -o outputfilename -g
	 *解释：
	 *	第一行是代表编译生成outputfilename文件所需要那些文件
	 *	第二行是编译命令，注意其前面一定要有一个tab
	 *注意：
	 *	在第一行中如果存在非.c的文件，
	 *	需要下面按着格式写明该文件的编译
	 */
	
	hello.out:hello1.o hello2.o hello12.c
	        gcc hello1.o hello2.o hello12.c -o hello.out -g
	        
	hello1.o:hello1.c
	        gcc hello1.c -o hello1.o -g
	        
	hello2.0:hello2.c
	        gcc hello2.c -o hello2.o -g

当makefile文件编写保存好之后，只需输入``make``命令就可快捷地进行编译。

# 五、拓展知识
linux下的命令也是一个个C语言的小程序，执行命令时会调用相应的程序

## 1.main()的真实写法应为：

	/*	
	 *	argv代表argc数组的长度，argc里面存储的是终端输入的命令，
	 *	每一个空格即增加一个长度，比如命令ls -l，该命令就会
	 *	存入argc数组中，而argv为2
	 */
	int main(int argv,char* argc[])

## 2.main函数中的return值代表该运行的成功与否

	return 0;//运行正常
	return 110;//返回110号错误

## 3.两条命令之间可以用``&&``来连接
第二条命令则仅在第一条命令执行成功的情况下执行。

## 4.linux将所有的资源或设备均看作一个文件
比如标准输出输入流、错误流分别对应``stdout``、``stdin``、``stderr``三个文件，C语言中一旦引入stdio库就引入这三个文件。

	//printf("please input");
	fprintf(stdout,"please input");
	fscanf(stdin,"%d",&a);
	fprintf(stderr,"errormessage");
	/*	
	 *	注意上面的代码中的stdout,stdin,stderr
	 *	可以用任何其他文件替代
	 */

## 5.重定向
``./a.out 1>> a.txt``
上面的命令可以将a.out的正确的输出流stdout里的内容输出到a.txt中，``>>``是追加形式，``>``是覆盖的形式

``./a.out < input.txt``
从input.txt中读取输入流

``./a.out 1> a.txt 2> b.txt <input.txt``
表示正确的输出流输出到a.txt，错误的输出流输出到b.txt，并从input.txt中读取输入流

## 6.管道
``ls /etc/ |grep ab``
命令的意思是将``ls /etc/``命令的输出当作``grep ab``命令的输入，这样就可以列出/etc/目录下所有包含ab的文件或目录

``ps -e | grep ssh``
``ps``是列出当前运行的进程，上述命令即为列出包含ssh的内容

## 7.操作系统对内存的管理

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201217175313937.png)
注意：其中栈底是高地址，栈顶是低地址。

