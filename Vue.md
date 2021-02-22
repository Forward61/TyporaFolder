Node

查看版本



设置淘宝源

https://blog.csdn.net/qq_35430000/article/details/90606641









### Vue



就算之前你装了webpack，那肯定是非全局安装

所以要全局安装 npm install --save-dev webpack









## Element-Vue

##### ELECTRON-VUE文档

#### https://electron.org.cn/vue/index.html

环境配置版本

![image-20210222223325447](https://i.loli.net/2021/02/22/Dr4UC9JW3Swutjc.png)



# [electron中Unable to install `vue-devtools`的解决方法](https://www.cnblogs.com/william1994/p/13894822.html)

https://www.cnblogs.com/william1994/p/13894822.html





<span>electron-vue报错：Webpack ReferenceError: process is not defined</span> 

![image-20200612204627022](https://img2020.cnblogs.com/other/1973296/202006/1973296-20200612205449874-1292808545.png)

#### 问题说明

在搭建electron的项目的时候出现了这样的问题，原因大概就是node.js的版本问题，在nodejs的11版本没有出现这样的问题，一般是nodejs的12版本出现此问题

#### 问题解决

在`.electron-vue/webpack.web.config.js` 和 `.electron-vue/webpack.renderer.config.js`下的HtmlWebpackPlugin添加一段代码











# 新版的vue cli默认没有自动创建router.js 和 store.js

https://www.jianshu.com/p/118f4df11e09









windows下jenkins的启动与关闭


1、用管理员身份启动cmd，否则执行命令报错：否则会报系统错误5

2、进入jenkins安装根目录

启动命令：

net start jenkins
关闭命令：

net stop jenkins