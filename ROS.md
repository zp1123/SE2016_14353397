ROS的配置
一．实验原理
ROS是一个机器人软件操作平台，前身由斯坦福大(Stanford Artificail Intelligence Laboratory)所研发。
它提供一些标准操作系统服务，目前主要支持Ubuntu操作系统。ROS可分为两层，低层是操作系统层，高层是实现不同功能的软件包。

ROS文件系统的概念：
Packages: 它位于ROS软件的最底层，可以包含任意的东西: libraries,tools,executables,etc.
Manifest: 是package的描述。其最重要的角色是定义packages之间的依赖关系（manifest.xml）。
Stacks: 它是package的集合，是一个更高层的library。
Stack Manifest: stack的描述（stack.xml）。
setup.sh文件设置ROS工作区的环境变量。
source ~/setup.sh：将设置永久化。
此时键入 echo $ROS_PACKAGE_PATH 指令，会看到类似于 
home/user/ros_workspace:/opt/ros/electric/stacks的路径。
二、配置unbantu仓库过程
首先配置ubantu的仓库环境，按照https://help.ubuntu.com/community/Repositories/Ubuntu 网址上的指示一步一步进行操作即可
三、实验步骤
1.设置计算机从packages.ros.org接受软件，ROS Jade只支持Trusty (14.04), Utopic (14.10) 和Vivid (15.04) 为Debian软件包
sudo sh -c 'echo  	"deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) 	main" > /etc/apt/sources.list.d/ros-latest.list'
2.设置钥匙
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
3.安装
sudo apt-get update
4.桌面完全安装
sudo apt-get install ros-jade-desktop-full
5.初始化rosdep：在可以使用ROS，需要初始化rosdep。rosdep可以很容易地安装系统依赖源要编译和运行所需的一些核心部件在ROS。
sudo rosdep init
   rosdep update
6.环境设置：如果ROS环境变量自动添加的每一个新的壳是为了bash会话很方便：
echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
	source ~/.bashrc
7.Getting rosinstall：rosinstall是ROS，分别分布常用的命令行工具。它使得可以轻松地下载多个源树的一个命令的活性氧包。
在Ubuntu中安装这个工具，运行：
sudo apt-get install python-rosinstall
四．实验结果
判断是否配置成功：输入指令roscore，使用ROS的第一件事情就是运行roscore命令，得到下图：
  https://ooo.0o0.ooo/2016/11/11/5825b3ad84345.png(图片链接）
五．实验感想
其实这次实验就是一个简单的配置过程，当然，前提是没有出现各种bug。我的整个过程还算很顺利，除了电脑本身容易死机，
网速太卡导致实验配置很花费时间外，基本上没有什么bug就配置完了ROS。不过说实话，可能是我课堂是没怎么听ＴＡ讲课，因为配置完整个ＲＯＳ，
看本次实验配置的ＰＰＴ，还是不怎么明白这次实验的用意。也没有查找到更多相关的知识点。
