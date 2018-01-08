## 系统设计

这是融合数据管理和多机器人协同SLAM的系统的详细设计文档，

### 系统的要求，限制，系统的假设

目标：解决多机器人定位的问题，可以使用预先创建的地图

系统资源开销尽可能的小，最好能够封装成函数库的形式，提供接口可以被调用，其中包含

重用ORB-SLAM中的线程模块（tracking， localmapping， loopclosing）

模块封装好，模块之间的较小依赖

SLAM库，主要包括两个命名空间，client + server

SLAM库中的传输应该使用虚函数，实例化去继承，与ROS能够独立出来

是一个lifelong mapping 的问题，其中涉及到了 pre-existing map 问题

![classDesign](images/2018/01/Google-catrographer.jpg){:height="50%" width="50%"}


### 特征选择

使用ORB特征，ORB特征的使用包含在整个的SLAM系统中，ORB特征的相关计算模块主要包括：
  * ORB特征提取，算法详细过程[戳链接](http://m.blog.csdn.net/zouzoupaopao229/article/details/52625678)
      |   |  
    --|---|--
      |   |  
      |   |  
      |   |  

  * ORB特征匹配
  * ORB Vocabulary

### 1. 数据结构设计

* 关键帧

* 地图点

*

### 数据管理方法的设计需要一个简洁的数据管理方法

用网格的方法去实现，可以对数据结构进行一定程度的改变，



### 词袋的作用，因为其太消耗运行时的内存空间，可以通过增加计算时间或者降低匹配的成功率来替代。

检索相似关键帧，并且计算关键帧之间的相似度
