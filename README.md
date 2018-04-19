#引言
Cycript是一个可以调试App的一个工具，目前只是了解到实时的去调试App上的内容； 待补充。。。
![支持的语言](https://upload-images.jianshu.io/upload_images/7980283-81f0fdd544cc7058.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##配置环境

###一 下载SDK 解压到本地
首先需要安装Cycript, 点击[Cycript官网](http://www.cycript.org/)下载最新的SDK包。
![Cycript SDK 下载到本地](https://upload-images.jianshu.io/upload_images/7980283-02d1e52bcb6d5bd8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
直接解压到本地，放到自己指定的目录，我在这里放到了 /opt 下面

###二 配置Cycript的链接
呼出 `Cycript`环境
- 解压完成，我们可以`cd`到本地目录，调用`cycript`命令
- 需要配置其环境变量调用`cycript`命令
**正确操作**
![呼出环境](https://upload-images.jianshu.io/upload_images/7980283-46526ba611bb3052.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**错误提示**
![报错](https://upload-images.jianshu.io/upload_images/7980283-fa94804072925f3d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
向`~/bash_profile`添加环境变量
```
  export CYPATHDIR=/opt/cycript
  PATH = CYPATHDIR:原有内容
```
**至此完成**

####遇到问题
![ruby版本过高](https://upload-images.jianshu.io/upload_images/7980283-ae24d61bfbdc2ac2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
ruby版本过高，需要下载旧版本的ruby，因为cycript中的配置的ruby是2.0中的文件，需要修改的内容比较繁琐，以及不确定性，直接🔗一个当前版本的`librubyXX.dylib`,🔗之前需要创建`cycript`中用到的目录文件
```
sudo mkdir -p 
#创建目标目录
/System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/lib/
#🔗源文件
sudo ln -s /System/Library/Frameworks/Ruby.framework/Versions/2.3/usr/lib/libruby.2.3.0.dylib /System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/lib/libruby.2.0.0.dylib
```



