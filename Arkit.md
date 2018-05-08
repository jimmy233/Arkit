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

## 第二周进展：
1.大致看了一遍 Fall2017 wwdc大会上的两个视频：Face Tracking with ARkit 以及 Introducing ARKit:<br>
对于Face Tracking，它仅在带有深度前置前置摄像头的iphone x上才有，当运行面部追踪会话时，会话使用前置摄像头检测到用户脸部时会自动将面部添加到ARFaceAnchor对象的锚点列表中。追踪脸部在世界坐标系中的位置和方向，继承而来的transform属性描述了人脸在世界坐标中的当前位置和方向；也就是说，在相对于会话配置的worldAlignment属性指定的坐标空间中。使用此变换矩阵将虚拟内容放置到AR场景的脸部。网上查找的一个demo利用此项技术主要是实现人脸京剧变脸且目前仅支持单人，目前看来在项目中的可用性不是很高。<br>
2.在项目中我们需要在人脸处实现一些AR处理，在对官方文档阅读和下载了几个demo后，关键在于实现能够返回人脸在世界坐标系中的位置，这样就能够将我们想要放置的一些虚拟物体放置特定坐标处。在官方文档中有一篇是关于：Detect known 2D images in the user’s environment, and use their positions to place AR content. 其实识别后的人脸 就可以看作一个 2D image，得到位置即可进行AR处理。(demo对ios版本有要求，还在更新。。。)。虚拟物体的动态处理：对于虚拟3D物体（使用 SceneKit渲染），2D物体（可采用SpriktKit渲染). 物体的动态实现：3D animated (暂时了解到是这样)<br>




