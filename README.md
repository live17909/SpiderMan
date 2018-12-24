# SpiderMan


SpiderMan能为您做的：

* Debug环境可以在手机上显示崩溃信息，分享给相关开发人员~
* 再也不用担心测试妹妹给你重现怎么操作崩溃的啦！
* 再也不用担心产品相关人员给你说哪儿哪儿崩溃，但是又重现不了的尴尬啦！
* 再也不用担心某些Rom禁止异常输出啦！
* 再也不用担心开发工具log信息时灵时不灵啦

|                          Debug环境                           |                            Share                             |      |
| :----------------------------------------------------------: | :----------------------------------------------------------: | ---- |
| ![](https://simple-bucket-1257044365.cos.ap-chongqing.myqcloud.com/debug.gif) | ![](https://ws1.sinaimg.cn/mw690/00677ch9gy1ftoekwmvl3j30af0hygof) |      |


## 引入依赖

```groovy
debugImplementation 'com.simple:spiderman:1.0.8'
releaseImplementation 'com.simple:spiderman-no-op:1.0.8'
```

## 初始化

放到Application的`onCreate()`初始化中，因为static了传入的context，并且放在其他Library初始化的前面

```java
public class App extends Application {
    
    @Override
    public void onCreate() {
        super.onCreate();
		//放在其他库初始化前
        SpiderMan.init(this);
    }
}
```


## 版本迭代

* 1.0.8 发现很多小伙伴不会代理异常收集，所以删除了异常回调
* 1.0.7 删除spiderman-no-op never-crash，优化报错类型显示
* 1.0.6 增加spiderman-no-op
* 1.0.5 奔溃文本分享美化排版
* 1.0.4 崩溃输出改为error级别
* 1.0.3 增加 拷贝/分享 崩溃文字/图片信息
* 1.0.2 重构，新增设备信息
* 1.0.1 去除 allowBackup，label
* 1.0.0 首次上传

