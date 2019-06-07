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

## Flutter项目在 Resolving dependencies 时卡住的解决办法
这个问题分为两种情况：
这种情况分为两种可能性：

仓库不可访问导致，由于google() 这个仓库地址是： https://dl.google.com/dl/android/maven2/com/ ，可能会出现无法访问的情况，		这时候只需要优先使用国内的阿里云仓库就可以了；
需要注意的是，使用的classpath 的gradle版本要可用，阿里云仓库不一定有最新的gradle 版本，具体版本在 阿里云仓库 中对应的参考目录下查找， 查找规则为：com/android/tools/build/gradle/， 如果不存在会导致下载失败；

想要设置仓库，只要在文件目录的/android/build.gradle 文件中，将buildscript 的repositories 字段改成如下代码即可：
```
maven{ url 'https://maven.aliyun.com/repository/google'}
maven{ url 'https://maven.aliyun.com/repository/gradle-plugin'}
maven{ url 'https://maven.aliyun.com/repository/public'}
maven{ url 'https://maven.aliyun.com/repository/jcenter'}
google()
jcenter()
```

设置了本地代理导致访问仓库时，走了本地代理而出现connetion refused 的情况，这种情况下只要在 /android/gradle.properties 文件中，添加或修改一下代码即可，如果配置了shadowsocks， 也可以自己配置host 和port;systemProp.http.proxyHost=

systemProp.http.proxyPort=
systemProp.https.proxyHost=
systemProp.https.proxyPort=

