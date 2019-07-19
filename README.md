# Ionic 文档

## 目录

## 写在前面

此文档用于 Ionic 项目的 安装，创建，编译，打包。

### 1. 安装环境

#### 1.1 预先安装
请先安装   
[Node.js](https://nodejs.org/en/) [Angular Cli](https://angular.cn/cli)

#### 1.2 安装Ionic
```
npm install -g ionic
```

#### 1.3 安装 Cordova
```
npm install -g cordova
```

#### 1.4 查看是否安装成功
Windosws
```
ionic –v 
cordova –v
```
Mac OS
```
ionic -version 
cordova –version
```

### 2. 创建项目

启动一个新的Ionic应用程序非常简单。从命令行运行ionic start命令，CLI将处理其余的命令。
```
ionic start myApp tabs
```
这里myApp是项目的名称，tabs是启动器模板，项目类型是angular。

tabs不是唯一可用的项目模板。在所有项目类型之间，有三个可用的模板：

>tabs：基于标签的布局  
>sidemenu：基于侧面菜单的布局  
>blank：具有单个页面的空项目  

使用以下命令查看所有可用模板： 命令：
```
ionic start --list
```
[更多详情](https://ionicframework.com/docs/building/starting)


### 3. 运行项目
Ionic应用程序在Web浏览器中运行
```
ionic serve
```
模拟 手机运行界面
```
npm i @ionic/lab
//安装 lab
```
将运行命令改为
```
ionic serve --lab
```

### 4. 添加平台
Android
```
ionic cordova platform add android
```
Ios
```
ionic cordova platform add ios
```

### 5. 编译
Android
```
ionic build add android
```
Ios
```
ionic build add ios
```

### 6.模拟器中运行
Android
```
ionic emulate android
```
Ios
```
ionic emulate ios 
```

### 7.生成apk(未签名的apk）
```
cordova build -release android
```

## 后续内容待添加 20190704日




## 其他信息

### 文档地址

[Angular](https://angular.io)  
[Ionic](https://ionicframework.com/docs)

### 参考文献

一、[Ionic开发Android项目app基本步骤](https://blog.csdn.net/qq_32378595/article/details/79510261)  
二、[ionic3 底部Tabs切换菜单结合侧边栏sidemenu](http://www.ionic.wang/article-index-id-108.html)  
三、[ionic app 创建和运行调试](https://www.cnblogs.com/Caiyilong/p/8553040.html)  
四、[Unable to find command: cordova platfrom add android](https://blog.csdn.net/android_gjw/article/details/72864486)

## About 关于
Founder [Myetear](https://github.com/myetear)  
Creation time 2019-7-4  
Only for internal use, not for all.
