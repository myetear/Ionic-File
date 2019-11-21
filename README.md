# Ionic 文档

For reference only, not for everyone.
( 仅供参考,并不适用于所有人. )

## 前言
Author(作者) [Myetear](https://github.com/myetear)  
Original address(原始地址) : https://github.com/myetear/Ionic-File  
Angular CLI: 8.1.2  
Ionic CLI 5.2.3

> 公开文档暂停更新
> 


## 目录
* [写在前面](#写在前面)
* [食用方法](#食用方法)
    * [安装环境](#安装环境)
    * [创建项目](#创建项目)
    * [运行项目](#运行项目)
    * [生成工程文件(添加平台)](#生成工程文件(添加平台))
    * [删除工程文件(移除平台)](#删除工程文件(移除平台))
    * [编译(Web程序)](#编译(Web程序))
    * [模拟器中运行](#模拟器中运行)
    * [生成apk(未签名的apk）](#生成apk(未签名的apk))
* [其他信息](#其他信息)
    * [Gradle](#Gradle)
    * [Gradle镜像加速](#Gradle镜像加速)
    * [Android-SDK](#Android-SDK)
    * [文档地址](#文档地址)
    * [参考文献](#参考文献)
    * [解决报错](#解决报错)
* [About](#About)

## 写在前面

此文档用于 Ionic 项目的 安装，创建，编译，打包。  
##### 由于暂时没有 MacOS 操作系统暂时忽略 IOS ,后期会添加缺少部分内容

# 食用方法

### 安装环境

#### 1 预先安装

> 请预先安装   
> * [Node.js](https://nodejs.org/en/) 
> * [Angular Cli](https://angular.cn/cli)  
> * [Gradle](#Gradle)  
> * [Android SDK](#Android-SDK) 
> * [JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html)   

> 选装
> * [Android Studio(免费)](#Android-Stuido)
> * [IntelliJ IDEA(社区版)](http://www.jetbrains.com/idea/)
> * [WebStorm(收费)](http://www.jetbrains.com/)  

注: 下载 Android Studio 会自动下载 Android SDK 和 Gradle

#### 2 安装Ionic
```
npm install -g ionic
```

#### 3 安装 Cordova
```
npm install -g cordova
```

#### 4 查看是否安装成功
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

### 创建项目

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


### 运行项目
Ionic应用程序在Web浏览器中运行
```
ionic serve
```
模拟 手机运行界面
```
npm i @ionic/lab  //安装 lab
```
将运行命令改为
```
ionic serve --lab
```

### 生成工程文件(添加平台)
Android
```
ionic cordova platform add android
```
Ios
```
ionic cordova platform add ios
```
> 工程文件生成在   
> .\platforms


### 删除工程文件(移除平台)
Android
```
ionic cordova platform rm android
```
Ios
```
ionic cordova platform rm ios
```

### 编译(Web程序)
#### Android
```
ionic build add android
```
#### Ios
```
ionic build add ios
```
> 编译成 WWW 文件夹下的JS文件  
> 如果执行 生成apk(未签名的apk , 将会自动生成Web程序

### 编译源码
```
ionic cordova build android
```

### 模拟器中运行
Android
```
ionic cordova run android // 可以向 模拟器 或 手机 安装

ionic cordova emulate android / /未确定命令用处
ionic emulate android // 未确定命令用处
```
Ios
```
ionic cordova run ios // 尝试使用这个

ionic cordova emulate ios // 未确定命令用处
ionic emulate ios // 未确定命令用处
```
> 暂时无法使用这个命令 会报错
> ```
> [ERROR] Unable to find command: emulate android
> ```  
> 解决:  尝试使用一下命令
> ```
> ionic cordova run android[ios]
> ```

### 生成apk(未签名的apk)
先执行编译安卓代码 再进行打包
```
ionic cordova build android --release
```

直接打包
```
cordova build -release android 
```
> 如果编译出现如下报错 请安装Gradle,或直接使用 Android Stuido 打开工程文件   
> 安装方法:[Gradle](#Gradle)
> 
> ```
> Could not find an installed version of Gradle either in Android Studio,
> or on your system to install the gradle wrapper. Please include gradle
> in your path, or install Android Studio
> 
> ```

### 修改图标
```
ionic cordova resources
ionic cordova resources ios
ionic cordova resources android
```

#### 安装 cordova-res
```
npm i -g cordova-res
```

### 修改名称
./config.xml 
```
 <name>名字</name>
 <description>app描述</description>
 <author email="email@email.com" href="http://example.com/">作者信息</author>
```


## 其他信息

### Gradle
推荐使用 4.10.3 [Gradle 镜像加速](#Gradle镜像加速)
#### 下载地址
> 官方: https://gradle.org/releases/    
> 个人: [4.10.3](https://lcloud-1252650524.cos.ap-beijing.myqcloud.com/gradle-4.10.3-all.zip)


#### 安装
> 将文件解压即可

#### 环境变量
> 解压路径 \gradle-4.10.3  
> GRADLE_HOME -> E:\Environmental\.gradle  
> Path -> %GRADLE_HOME%\bin

#### 放入文件
> 将文件放到啊这个路径下面 并解压
>  C:\Users\xxx\.gradle\wrapper\dists\版本\乱码

### Gradle镜像加速
>  找到 C:\Users\UserName\.gradle
>  新建文件 init.gradle
>  将以下内容保存到文件
> ```
> allprojects{
>    repositories {
>        def ALIYUN_REPOSITORY_URL = 'http://maven.aliyun.com/nexus/content/groups/public'
>        def ALIYUN_JCENTER_URL = 'http://maven.aliyun.com/nexus/content/repositories/jcenter'
>        all { ArtifactRepository repo ->
>            if(repo instanceof MavenArtifactRepository){
>                def url = repo.url.toString()
>                if (url.startsWith('https://repo1.maven.org/maven2')) {
>                    project.logger.lifecycle "Repository ${repo.url} replaced by $ALIYUN_REPOSITORY_URL."
>                    remove repo
>                }
>                if (url.startsWith('https://jcenter.bintray.com/')) {
>                    project.logger.lifecycle "Repository ${repo.url} replaced by $ALIYUN_JCENTER_URL."
>                    remove repo
>                }
>            }
>        }
>        maven {
>                url ALIYUN_REPOSITORY_URL
>            url ALIYUN_JCENTER_URL
>        }
>    }
> }
> ```

### Android-SDK 
> 可以尝试安装 [Android Stuido](#Android-Stuido) 会自动下载 SDK

#### 环境变量 
请根据自己安装的位置替换 - 后的内容
> ANDROID_HOME - E:\Sdk  
> ANDROID_SDK_ROOT - %ANDROID_HOME%  
> ANDROID_AVD_HOME - E:\Environmental\.android\avd  
> ANDROID_SDK_HOME - E:\Environmental\  

### Android-Stuido
一、 使用 [jetbrains](https://www.jetbrains.com) 的 [Toolbox](https://www.jetbrains.com/toolbox/app/?fromMenu) 下载 Android Stuido

二、 在 [developer](https://developer.android.google.cn) 中下载 [Android Studio](https://developer.android.google.cn)
### 文档地址

[Angular](https://angular.io)  
[Ionic](https://ionicframework.com/docs)  
[cordova](https://cordova.apache.org/)

### 参考文献

一、[Ionic开发Android项目app基本步骤](https://blog.csdn.net/qq_32378595/article/details/79510261)  
二、[ionic3 底部Tabs切换菜单结合侧边栏sidemenu](http://www.ionic.wang/article-index-id-108.html)  
三、[ionic app 创建和运行调试](https://www.cnblogs.com/Caiyilong/p/8553040.html)  
四、[Unable to find command: cordova platfrom add android](https://blog.csdn.net/android_gjw/article/details/72864486)  
五、[@ionic/lab](https://www.npmjs.com/package/@ionic/lab)
六、[修改名称/图标](https://blog.csdn.net/qq_30100043/article/details/54985045)


### 解决报错

#### @angular-devkit/build-angular:browser
错误描述:  
An unhandled exception occurred: Could not find the implementation for builder @angular-devkit/build-angular:browser  

修复办法:  
>安装 yarn add @angular-devkit/build-angular


## About
Founder [Myetear](https://github.com/myetear)  
Creation time 2019-7-4  
Only for internal use, not for all.
