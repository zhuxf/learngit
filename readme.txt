第一：Android Handler消息机制原理

通过Handler消息机制来实现子线程和主线程之间的通信；
简单总结：子线程获取到数据后，不直接进行UI更新，而是把数据“装”到消息中发送到主线程，主线程中有一个循环轮询会立即收到子线程发来的信息，然后拿到消息数据后再主线程更新UI。

做法：通常是在主线程new一个handler,然后在子线程通过handler来发送消息。最终是在行的了乳的handleMessage()方法中处理子线程发过来的数据消息，直接进行UI更新。

Handler消息处理者:1:处理Message;2:发送Message,并将某个Message压入到MessageQueue。
Looper轮询器:在Looper里面的loop()函数中有个死循环，它不断的从MessageQueue中取出Message，然后传给handler进行处理，如此循环往复。假如MessageQueue队列为空，那么它会进入休眠。
MessageQueue消息队列:这个集合装有很多Runnable、Message。

子线程new一个handler的步骤：
1、Looper.prepare();调用这个方法，会创建一个Looper对象，在子线程中创建一个Handler，它首先调用Looper.prepare()方法时，创建Looper对象是新的，与主线程不同。
2、实例化Handler，在构造方法中实现handleMessage(Message msg)处理消息
3、Looper.loop();
handler最终是通过handleMessage(Message msg)来处理消息
handler.sendMessage(Message msg)来发送消息(Handler还负责将某个消息压入MessageQueue中发消息)


Android网站推荐
http://www.zhihu.com/question/19611325
开源库和工具大全：http://android-arsenal.com/
在线看源码：http://www.grepcode.com/
投票最多的几个问题，空闲时看看：http://stackoverflow.com/questions/tagged/android?sort=votes
Android有空必须看：http://www.trinea.cn/android/android-open-project-summary/
Android开发需要的sdk、开发用到的工具、设计规范等等下载：http://www.androiddevtools.cn/
 Android Annotations
 AnimatorCompat
 Material Design:Lobsterpicker
 RxFlux
 Android-UCToast
 FlowingDrawer
 ProgressRoundButton	
 ScrollDownLayout	
 RichText
 AnimatedRandomLayout

 1.android studio 打aar依赖包，并使用
 2.Picasso 源码，代码简单，逻辑清晰
 3.leakcanary检查内存泄露工具，适用android和java：https://github.com/square/leakcanary
 4.插件化开发：淘宝的 Atlas和360 的 DroidPlugin
 5.结构之法 算法之道:http://blog.csdn.net/v_july_v/article/details/19131887
 6.Rxjava https://github.com/lzyzsd/Awesome-RxJava;(http://gank.io/post/560e15be2dca930e00da1083)
 7.框架：http://casatwy.com
 8.Android生成唯一标识符UUID （http://m.blog.csdn.net/blog/wd40296/17117519）
 9.Android开发技术周报：http://toutiao.io/posts/65a2mn
 10.Android开发技术周报：http://www.androidweekly.cn/tag/androiddevweekly/
 11、汇集了众多不同类型的工具、库和可浏览索引的资源：http://www.androidviews.net/
 12、Android学习资料(全)：http://toutiao.io/r/6mm40
 13、Android Studio、gradle基础入门知乎：https://www.zhihu.com/question/27866554/answer/38427122
 14、美团技术团队：http://tech.meituan.com/
 15、Android性能测试工具介绍：http://toutiao.io/posts/x7nqxf
 16、Android学习资料(干货)：http://www.importnew.com/3988.html
 17、Materialdrawer：http://mikepenz.github.io/MaterialDrawer/
 18、Github开源Android组件资源整理（一） 个性化控件(View):http://blog.csdn.net/oyangyujun/article/details/43340739
 19、Rxjava使用手册中文翻译版：	http://rxjava.yuxingxin.com/index.html
 20、推荐应用：https://www.zhihu.com/question/31476726
 21、gradle 版本：https://jcenter.bintray.com/com/android/tools/build/gradle/

 1、Android Studio
 2、React Native
 3、Sky
 4、MVP模式、MVVM模式、RxAndroid/RxJava
 5、Hybrid
 6、Material Design (github 关注的)
 7、Sketch
 ==================================2015 end===============================================
 ==================================2016 start=============================================
 
 1、learning git 02-14