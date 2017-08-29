
# tensorflow

### 搭建开发环境C#

- windows, vstudio, nuget tensorflowsharp https://github.com/migueldeicaza/TensorFlowSharp/
- c++ tutorial https://tebesu.github.io/posts/Training-a-TensorFlow-graph-in-C++-API
  - c++ load & train https://medium.com/jim-fleming/loading-a-tensorflow-graph-with-the-c-api-4caaff88463f
- c++ build graph https://github.com/tensorflow/tensorflow/blob/master/tensorflow/cc/tutorials/example_trainer.cc

### c++ <-> c# mapping

- tfgraph 包含scope的设置
- tfgraph 包含所有的操作 http://www.jianshu.com/p/65dc64e4c81f
  - 操作定义为完成计算 TFOperation
  - placeholder返回tfoperation，参考tfsharp里面的代码例子: tfoperationdesc的使用方法
  - TFOperationDesc可以对placehoder、variable, scalarconst进行操作
- 读入文件，使用tfbuffer，tfgraph和tfbuffer对接，tfbuffer可以通过binary和文件对接
- tftensor可以采用C# Array初始化，设定数组的维数和类型: var w = graph.Variable(graph.Const(new TFTensor(new float[784, 10])));
- tfoperation可以初始化tfoutput，session.run()的输入是tfoutput，据文档说明，可以用TFOperationDesc创建tfoperation，但未找到例子

### mnist sample

- graphdef
  - 参考例子，如何定义计算的公式：https://github.com/tensorflow/tensorflow/blob/master/tensorflow/cc/tutorials/example_trainer.cc
  - 一个线性计算的公式定义：参考 tfsharp: SampleTests: LinearRegression()
- load & run
  - 训练运行步骤：
    - 创建session(graph)
    - 输入变量tensor，循环训练次数
    - 输入计算过程中的变量值
    - 如何定义训练策略？何时退出？如何使用测试集？
  - 预测运行步骤：参考tensorflowsharp中Inception Example

# 缺陷检测
