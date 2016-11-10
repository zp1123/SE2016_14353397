# SE2016_14353397
                                 DOL开发环境配置
1.实验原理
 1.1分布式操作层： 
  分布式操作层（DOL）是一个程序的并行应用软件开发框架。DOL允许指定基于计算Kahn进程网络模型的应用范围和特点，基于SystemC仿真引擎。
此外，劳工部提供了基于XML规范的格式来描述一个多处理器系统上的并行应用程序的实现，包括结合和映射。
     https://ooo.0o0.ooo/2016/11/10/58246fa4928d3.png （图片上传网址）
 1.2 Make工具简介
  在Linux和Ubuntu环境中，make工具主要被用来进行工程编译和程序链接
  Makefile文件：告诉make以何种方式编译源代码和链接程序
  make通过比较对应文件（规则的目标和依赖）的最后修改时间，来决定哪些文件需要更新、那些文件不需要更新。
 1.3 Ant工具简介
  Ant是一种基于Java的build工具。
  Ant用Java的类来扩展。
  Ant本身就是这样一个流程脚本引擎，用于自动化调用程序完成项目的编译，打包，测试等。
 1.4 Ant的优点
  跨平台性。Ant是纯java语言编写的，所示具有很好的跨平台性。
  操作简单。Ant是由一个内置任务和可选任务组成的。Ant运行时需要一个XML文件(构建文件)。
  容易维护和书写，结构清晰。
  Ant可以集成到开发环境中。
 1.5 Java与javac简介
  用途：编译或执行java代码
  javac命令用来编译java文件
  java命令可以执行生成的class文件
2.实验步骤
 2.1安装一些必要的环境(ubuntu为例)：
  $	sudo apt-get update
  $	sudo apt-get install ant
  $ 	sudo apt-get install openjdk-7-jdk
  $	sudo apt-get install unzip
 2.2解压文件
  新建dol的文件夹 
  $	mkdir dol
  将dolethz.zip解压到 dol文件夹中
  $	unzip dol_ethz.zip -d dol
  解压systemc
  $	tar -zxvf systemc-2.3.1.tgz
 2.3编译systemc
  解压后进入systemc-2.3.1的目录下
  $	cd systemc-2.3.1
  新建一个临时文件夹objdir
  $	mkdir objdir
  进入该文件夹objdir
  $	cd objdir
  运行configure(能根据系统的环境设置一下参数，用于编译)
  $	../configure CXX=g++ --disable-async-updates
  运行configure之后的截图:
  https://ooo.0o0.ooo/2016/11/10/582471003b615.png
  编译
  $	sudo make install
  编译完后文件目录如下($ cd ..        $ ls
  https://ooo.0o0.ooo/2016/11/10/5824717160c7d.png
  记录当前的工作路径(会输出当前所在路径，记下来，待会有用)
  $	pwd
  https://ooo.0o0.ooo/2016/11/10/582471a6293ed.png
 2.4.编译dol
  进入刚刚dol的文件夹
  $	cd ../dol
  修改build_zip.xml文件
  找到下面这段话，就是说上面编译的systemc位置在哪里，
  <property name="systemc.inc" value="YYY/include"/>
  <property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
  把YYY改成上页pwd的结果（注意，对于  64位 系统的机器，lib-linux要改成lib-linux64）
  然后是编译
  $	ant -f build_zip.xml all
  若成功会显示build successful

  接着可以试试运行第一个例子
  进入build/bin/mian路径下
  $	cd build/bin/main
  然后运行第一个例子
  $	ant -f runexample.xml -Dnumber=1

  成功结果如图
  https://ooo.0o0.ooo/2016/11/10/5824722f04aa0.png(当时那张图片没有找到，所以上传了一张ppt里面的图片）
3.实验感想
  到目前为止，实验过程中在安装ＤＯＬ环境的时候，总是在需要过程截图的地方出现不一样，个人虽然前面有学过操作系统，
  但是还是觉得挺困难，最后在ＴＡ的帮助下完成了ＤＯＬ的环境配置。GIT的安装这次实验 一直以为会很困难（因为上课TA讲了好多东西，
  而我坐在后面并没有听懂什么），但是后来接触百度呀问TA或者同学。其实还可以，做出来了很有成就感。






