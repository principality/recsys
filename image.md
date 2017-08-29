

# 图像识别与深度学习

- 机器视觉
- 图像相关算法
- 深度学习相关算法

### 有用的URL

http://blog.csdn.net/u010402786/article/details/49272757 如何调整CNN
  - 优化输入
  - 优化结构：异构神经元
https://zhuanlan.zhihu.com/p/21403924 缺陷检测在电力行业的应用
https://zhuanlan.zhihu.com/p/23923248 三维建模，整合人脸特征：如何识别人脸特征
https://www.zhihu.com/question/30694287 机器人与深度学习（不知道机器结构的时候如何让机器实现功能）
https://mp.weixin.qq.com/s/tCUpGC01z13wtO-CMT2V3w tensorflow的55个经典案例
https://mp.weixin.qq.com/s/b3M0Y-HF3aom1ztv3Qnwig 图像识别方向的多种网络
https://zhuanlan.zhihu.com/p/27424282?utm_source=wechat_session&utm_medium=social kaggle参赛经验
http://tensorlayercn.readthedocs.io/zh/latest/user/tutorial.html#word-embedding 教程
https://public.tableau.com/profile/mckinsey.analytics#!/vizhome/AutomationandUSjobs/Technicalpotentialforautomation 人工智能可以发展的方向

### 优化笔记

- 防止梯度消失：层数过多，反向梯度效应加剧，修改为ReLU/maxout等函数，可以增强网络深度
- 减少DNN网络的过度参数：提取特征，减少噪音
- 防止样本的噪音特征被识别：加入噪音
- 停训标准：训练LOSS越来越好，但是测试集LOSS变糟糕，采用EARLY STOPPING方式进行处理（如3次测试集LOSS降低，则停止）

### 防止过拟合

https://www.douban.com/note/269320384/

- 选择合适的样本集（加大样本集？合适的训练集？提高训练质量？）
  - 图像预处理：超像素分割
- 在训练数据的基础上，提供一套验证数据
- 人工处理，减少（无效）特征（避免对噪音的过度敏感）
  - 小波过滤
- 使用权值衰减方式？

### 各种网络&图像网络的比较

- DNN无法对时间序列上的变化进行建模（RNN）
- 面向更多的类型识别：ImageNet
- 面向更精细的特征识别：机器视觉

### 超参数

http://www.cnblogs.com/neopenx/p/4768388.html

神经网络经典五大超参数:

学习率(Leraning Rate)、
权值初始化(Weight Initialization)、
网络层数(Layers)
单层神经元数(Units)、
正则惩罚项（Regularizer|Normalization)
