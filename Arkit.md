# Arkit
## 第一周了解：
1.这周主要是先了解了Arkit框架一种是基于3D场景(SceneKit)实现的增强现实，一种是基于2D场景(SpriktKit)实现的增强现实：<br>
根据简书arkit教程中给出的示例代码 简单运行了arkit程序，体验了3d效果以及2d效果。<br>
2.了解了arkit的基本工作原理，它提供了两种虚拟增强现实视图，分别是3d效果以及2d效果，且均以相机图像作为背景视图，在这上感觉很合适我们的项目。<br>
Arkit中一个非常重要的类 Arsession类，负责搭建桥梁：ARWorldTrackingSessionConfiguration与ARFrame。<br>
ARWorldTrackingSessionConfiguration（会话追踪配置）的作用是跟踪设备的方向和位置,以及检测设备摄像头看到的现实世界的表面。<br>
ARCamera只负责捕捉图像，不参与数据的处理<br>
3.框架工作流程：<br>
           1.ARSCNView加载场景 <br>
           2.场景启动相机ARCamera开始捕捉场景 <br>
           3.捕捉场景后ARSCNView开始将场景数据交给Session <br>
           4.Session通过管理ARSessionConfiguration实现场景的追踪并且返回一个ARFrame <br>
           5.给ARSCNView的scene添加一个子节点（3D物体模型）<br>
            图：<br>
              ![](https://upload-images.jianshu.io/upload_images/6271687-5b2cea6f7131d32e.png?imageMogr2/auto-orient/) 
        下周目标：了解Ar-kit自定义实现，进一步思考如何将框架合适的应用到项目当中。

