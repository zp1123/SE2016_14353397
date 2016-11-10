# SE2016_14353397
                                  Deadlock 死锁
1.实验步骤
  1.1将ppt文档上面的代码打到Deadlock.java文件中
      https://ooo.0o0.ooo/2016/11/10/582477e52a87e.png
  1.2 在cmd中运行，首先进入到Deadlock.java的路径中，输入javac Deadlock.java编译java文件，生成.class文件。
  1.3Windows系统下，将ppt文档上的Deadlock.bat文件的代码内容打到记事本里，然后保存
     https://ooo.0o0.ooo/2016/11/10/582478dfcf990.png 
  1.4将该批处理文件放在java程序Deadlock.class目录下，双击运行，观察结果。发生死锁时的运行截图如下所示，运行到213次时发生死锁：
     https://ooo.0o0.ooo/2016/11/10/58247843540e8.png
2.产生死锁的四个必要条件
  2.1 互斥条件：一个资源每次只能被一个进程使用。如果另一进程申请该资源，那么申请进程必须等到该资源被释放为止。
  2.2请求与保持条件：一个进程因请求资源而阻塞时，对已获得的资源保持不放。
  2.3 不剥夺条件:进程已获得的资源，在末使用完之前，不能强行剥夺。
  2.4循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系。
3.实验总结
  3.1程序产生死锁的原因
在Deadlock.java文件中，将函数的类型用关键字synchronized申明了，当用该关键字修饰一个方法或者一个代码块的时候，能够保证在同一时刻最多 只有一个线程执行该段代码；当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步 代码块或同步方法的访问将被阻塞。所以当本次实验的Deadlock程序运行时，a.methodA(b)执行时需要访问class B的代码段，b.methodB(a) 执行时 需要访问class A的代码段，当这两个处于不同线程的函数同时开始执行时，都会因为请求访问的代码段被占用而同时被阻塞，也就是进入了循环等待， 死锁产生。
 3.2实验感想
在编译Deadlock.java文件上传，生成.class文件的时候，进入Deadlock.java的路径，然后输入命令行javac Deadlock.java报错
  https://ooo.0o0.ooo/2016/11/10/582478fd9aab6.png
原因是环境变量里面的路径没有设置好，在系统变量path中添加C:\jdk-7u79-windows-x64\bin; 就可以了。

