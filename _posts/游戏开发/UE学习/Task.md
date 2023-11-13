



## 点位点击弹出框效果相关思路
[【精选】21虚幻4【UE4】鼠标碰撞检测(实现鼠标监听，从而实现点击场景模型(碰撞体)高亮函数)\_ue setrendercustomdepth\_Ezms的博客-CSDN博客](https://blog.csdn.net/qq_41260655/article/details/123013358)

(1)通过鼠标左键、中键、右键绑定点击事件

(2)通过函数**ConverMouseLocationWorldSpace** 将鼠标2D 位置转化为三维世界的坐标

(3)通过函数**LineTraceByChannel**根据点击的坐标位置，方向进行延申，形成一条射线，射中的第一个碰撞体接收命中的监测**OutHit**

(4)根据此Actor可设置其属性RenderCustomDepth高亮属性

[【UE4 Blueprint】使用射线检测在鼠标点击处生成物体\_ue4打印鼠标点击的物体-CSDN博客](https://blog.csdn.net/qq_31788759/article/details/89418283)

(1)生成一条从相机到鼠标点击位置方向的射线，在碰撞到的第一个 Location 生成 Actor 类

获得位置之后，在创建 UI 组件的时候，设置位置就行


## 像素流送
[[虚幻引擎][UE][UE5]像素流送(Pixel Streaming)，像素流去掉黑边和按钮[UE5.1.0]，鼠标控制\_涟涟涟涟的博客-CSDN 博客]( https://blog.csdn.net/weixin_43784914/article/details/127852696 )

[UE4.27 UE5 像素流送新人向教程，手把手带你避坑 - 知乎](https://zhuanlan.zhihu.com/p/566593290)

1. **解释一下像素流送程序快捷方式的后缀命令**  
    **-AudioMixer** 像素流送默认是没有声音的，所以想要有声音，这个必须记得添加  
    **-PixelStreamingIP=xxxx** 像素流送的IP地址，这个可以根据需要修改  
    **-PixelStreamingPort=xxxx** 像素流送端口，同理也是可以修改的  
    **-forceres**强制运行，后面长接分辨率指令  
    **-ResX=1920 -ResY=1080** 设定分辨率 不用多说  
    **-RenderOffScreen** 如果不想打开像素流送窗口也想让程序流送，就使用这个命令，关闭时候可以在任务管理器中结束程序
2. **4.27的stun/turn相关协议文件路径**  
    4.27其实是没有stun/turn文件的，需要打包一个已经开启像素流送插件的4.26空项目，然后找到release文件夹，复制这个文件夹过来用，这个方法是可行的。
3. **使用stun/turn的时候记得要开启19302 19303两个端口**  
    开启方法百度一大把。
4. **为了方便开启一大堆程序，可以写一个. Bat 文件来执行**

```bat
target.exe -PixelStreamingIP=localhost -PixelStreamingPort=7777
```