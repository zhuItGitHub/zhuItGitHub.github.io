---
layout:       post
title:        "Linux系统下安装jdk及环境配置（两种方法）"
date:         2017-07-12 12:00:00
author:       "zhuJianJian"
header-img:   ""
catalog:      true
multilingual: true
tags:
    - Linux
---

## 1:手动安装

###1.去Oracle官网下载需要安装的jdk版本，我这里用的是jdk-8u181-linux-x64.tar.gz
###2.将该压缩包放到/usr/local/jdk目录下，jdk目录需要自己手动创建，也可以叫java，名字自己随意取（见名知意），然后解压该压缩包，输入如下指令：tar zxvf jdk-8u181-linux-x64.tar.gz
###3.接下来就该配置环境变量了，输入以下指令进行配置：vim /etc/profile
输入完毕并回车，在文件尾部添加如下信息：

export JAVA_HOME=/usr/local/jdk/jdk1.8.0_181
export CLASSPATH=$:CLASSPATH:$JAVA_HOME/lib/ 
export PATH=$PATH:$JAVA_HOME/bin

###ps:注意：第一行的JAVA_HOME=/usr/local/jdk/jdk1.8.0_181 此处等号右边的是自己的jdk实际解压目录。如果不是该目录则需要改成自己的实际目录，其他不变。

###4.编辑完之后，保存并退出，然后输入以下指令，刷新环境配置使其生效：source /etc/profile
###5.查看jdk是否安装成功，输入指令java -version即可。
###6.至此，手动安装完成~