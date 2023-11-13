



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

