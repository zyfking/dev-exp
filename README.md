# dev-exp
常用知识总结

## Nginx参考资料

- [Nginx官网](https://nginx.org/en/download.html)
- [Nginx详解（正向代理、反向代理、负载均衡原理）](https://blog.csdn.net/tsummerb/article/details/79248015)
- [Nginx负载均衡的5种方式](https://blog.csdn.net/zhang6622056/article/details/82586936)



## Flutter学习资料
在iOS中需要安装cocoaPods,未安装会报错：
 error: The sandbox is not in sync with the Podfile.lock. Run 'pod install' or update your CocoaPods installation.

- [cocoaPods的安装和使用](https://www.jianshu.com/p/b656c3c59af5)
- [windows安装文档](https://blog.csdn.net/m075097/article/details/79639116)
- [macos安装文档](https://blog.csdn.net/wangjunling888/article/details/80768285)
- [linux安装文档](https://flutter.io/setup-linux/)


## Flutter常见问题
  Waiting for another flutter command to release the startup lock...解决办法
  
  打开AndroidStudio的时候顶部的模拟器一直是loading状态，即使已经打开了模拟器。 
  运行flutter doctor 提示
  Waiting for another flutter command to release the startup lock
  查了一下github的flutter issue 找到了解决方法，如下：
  1、打开flutter的安装目录/bin/cache/ 
  2、删除lockfile文件 
  3、重启AndroidStudio
  
【问题分析：】你开启新的flutter进程时，后台有一个flutter进程没有关闭，导致的冲突。

【解决方案：】关闭后台dart进程，关闭IDE，然后重新打开IDE，运行项目，运行到设备试试看，基本问题不大了。
（一句话：重启基本能解决问题）


## cocoaPods安装常见问题

- [解决Mac10.13 Pod报错 -bash: /usr/local/bin/pod: ](https://blog.csdn.net/xuyang844175181/article/details/79162068) 
