# webpack4_demo
基于webpack3升级webpack4的demo，配置模块按需加载，模块按需切割打包

### 一：背景
###### 因为项目功能越加越多，打包后的体积越来越大，导致首页展示的时候速度比较慢，因为要等压缩的js的包加载完毕。
首页展示的时候只需要对应的js，并不需要全部的js模块，所以这里就可以用按需加载，这里webpack4官方文档提供了模块按需切割加载，配合es6的按需加载import()方法，可以做到减少首页包体积，加快首页的请求速度，只有其他模块，只有当需要的时候才会加载对应js。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190515233354420.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTA2MzMyNjY=,size_16,color_FFFFFF,t_70)

这里我定义了三个界面（HelloWorld1，HelloWorld2，HelloWorld3），其中HelloWorld1用的impot()按需的方式，其他两个都是直接import。

再打包，终于成了，把HelloWorld1分离出来独立包`h-w1`：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190516005928373.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTA2MzMyNjY=,size_16,color_FFFFFF,t_70)

资料：

按需加载，模块按需切割打包博客：https://www.jianshu.com/p/90f9fec9fc34

webpack3升级webpack4博客：https://blog.csdn.net/u010633266/article/details/90025292
