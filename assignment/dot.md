## Lab 2 DOL实例分析&编程
###任务一：修改example2,让3个square模块变成2个
1.实验过程
 1.1 实验方法：
  修改xml的iterator文件，将3改成2.
 1.2实验操作：
  进入dol/examples/example2文件夹中，修改example2.xml。将value值由3改为2.
   ![](https://ooo.0o0.ooo/2016/11/11/5825b59f610b4.png)
 1.3实验结果：
  修改前是3个square 输出i^8
   ![](https://ooo.0o0.ooo/2016/11/11/5825b5b466d63.png)
  修改后，删除掉dol/build/bin/main里面的example2文件夹，然后运行example2，输出的是i^4：
   ![](https://ooo.0o0.ooo/2016/11/11/5825b5c9d14ed.png)
 1.4 example2的DOT图：
  修改代码前 example2的DOT图
   ![](https://ooo.0o0.ooo/2016/11/11/5825b5e11f3b3.png)
  修改代码后 example2的DOT图
   ![](https://ooo.0o0.ooo/2016/11/11/5825b5fbb8bae.png)
   
   
任务二：修改example 1，使其输出三次方数
2.实验过程
 2.1实验方法
  修改example 1 文件夹里面的square.c，把文件中计算的二次方改为三次方。
 2.2实验操作
  进入到dol/examples/example 1/src,修改src文件夹里面的square.c文件里面的代码，
   ![](https://ooo.0o0.ooo/2016/11/11/5825b614be8ed.png)
 2.3实验结果
  修改前运行example 1得到的实验结果
   ![](https://ooo.0o0.ooo/2016/11/11/5825b62bbb3ba.png)

  修改后运行example 1 得到的实验结果
    ![](https://ooo.0o0.ooo/2016/11/11/5825b63fbcd22.png)
 2.4 example 1 的DOT图
  修改代码前example 1 的DOT图
   ![]( https://ooo.0o0.ooo/2016/11/11/5825b65543ec7.png)
  修改代码后 example 1 的DOT图
    ![](https://ooo.0o0.ooo/2016/11/11/5825b666f41ea.png)
3.实验感想：
  本次实验由于上课ＴＡ对代码讲解很清楚，所以在修改代码的时候很顺利。但是之前dol配置已经成功后再次修改代码后按照之前配置的方法去跑example，
虚拟机会报错。原因是安装ubuntu是群公告里面师兄提供的，我这边在去操作的时候，权限不够，需要将权限转一下。在修改了example后，
run之前与run之后结果没有什么改变，原因是修改代码后run之前没有将dol/build/bin/main里面的文件夹删除掉，
里面的example是没有修改代码之前生成的，对结果会有影响。
