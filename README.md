# Termux-install-linux
用Termux安装不同发行版本的Linux

本人代码水平有限不书写脚本 会以详细的图文教程

大家都知道Termux能安装proot下运行的Linux

主要使用的是proot-distro这个方法

使用命令pkg install proot-distro

在使用proot-distro list查看可安装的Linux的时候发现，对应的发行版本不是自己想要的

（实际上是因为我自己在容器想用chrome-browser的时候发现，高版本的Ubuntu强推snap，可容器用不让用systemctl用不了snap）

这里我测试了发现Ubuntu18.04的chrome-browser可以完整安装，便准备安装Ubuntu18.04(bionic)

在上面说到使用proot-distro list查看可安装的Linux的时候发现，Ubuntu只有jammy

![image](https://user-images.githubusercontent.com/69832714/209115001-ab69fb2e-a489-4a45-bf1c-c59ae1d72177.png)

这时候就到文章的正文部分了

在手机里面找到proot-distro的安装源路径/data/data/com.termux/files/usr/etc/proot-distro下

找到想要修改的对应的系统镜像源，我这里是想要修改Ubuntu的镜像源

![image](https://user-images.githubusercontent.com/69832714/209116149-950b3e02-85e2-44b9-8b26-b525f8495e2b.png)

![image](https://user-images.githubusercontent.com/69832714/209117337-ebfe63c2-273e-4831-ba4c-029223d07659.png)

这里可以看到不同cpu架构的Ubuntu安装源的地址和SHA256值

可以在https://github.com/termux/proot-distro/releases/  中找到各种Linux不同发行版本的地址

当然如果缺少魔法的话，使用国内源(清华源、中科大源、阿里云、腾讯云等等)

修改源地址后，通过指令计算对应的SHA256并修改对应的值，并保存

格式：certutil -hashfile 绝对路径下文件 校验值 （Windows电脑）

最后使用proot-distro install ubuntu就大功告成了！
