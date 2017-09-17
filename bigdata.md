# 大数据

### 应用场景

大数据相关的场景比较多，常见的有：
- ETL（数据提取、转换、加载）、
- 实时流式（监控报警、风控等）、
- 机器学习（推荐引擎、用户画像等）、
- 非结构化分析（视频、图片、语音、文本等）、
- 海量大数据在线存储（HBase）、搜索及OLAP。
- 其中OLAP（在线联机分析）在很多企业占住分析类的大部分。

https://yq.aliyun.com/articles/198435

### 资料

- 大数据产品列表 https://zhuanlan.zhihu.com/p/21752798
- 数据仓库历史 https://zhuanlan.zhihu.com/p/26815743

### 组件套餐

- collector & etl
  - sqoop
  - flume
  - spider
  - data gateway
  - canal
- hbase/hbase-indexer/hadoop
- spark
  - spark sql jdbc/hbase rdd
  - spark hbase connector
  - deeplearning4j
  - Oozie ?
- zeppelin/superset/saiku
- kafka/gobbin -> hdfs?
- spring boot
- nagios?

**常见的开发场景**

- 数据接入
- hbase索引优化
- spark算法及实现
- 界面定制开发
- 应用接口

### 日志型组件套餐 ^ ^

- logstash
- cassandra & index plugin
- presto

### 收集的一些github项目

- openrefine
- extraction-framework
- webmagic
- kairos
- indexr
- ksql for kafka
- lily hbase indexer https://github.com/NGDATA/hbase-indexer
- nifty, thrift client/server
- boilerpipe, html extractor
- hanlp, corenlp, mallet

### 实施的坑

- 操作系统redhat/centos，注意要上raid(raid2, raid5?)，防止存储出问题
- 存储是否要上集中式存储，磁盘阵列或其他？
- 采用成熟的套件，cloudera/CDH?
- 需要对平台进行监控，配合成熟的监控工具？

### 数据中心

- 数据采集、清洗、整合
  - 模板化主动采集、清洗、过滤、转换（模板化有助于检测数据的样式）
  - 支持多种协议：WS/FTP/JDBC/...
  - 传输过程的加密？是否必要？通信白名单？
  - 实时监控、采集异常及时处理
  - 完整性、合理性校验，提供数据质量检验报告
  - 过程监督，进度报告
  - 结构化，半结构化，非结构化数据
  - 采集的时候，数据分散，格式不一，如何保证入库的完整完备？
- 数据存储：业务相关，合理分库分表，考虑上层计算以及海量存储的要求
- 数据分析与服务层：依赖OLAP引擎，提供REST接口？
- 应用服务层：根据具体业务，提供在OLAP基础上，各种需要的监测功能展示（BI层）
- 数据治理
  - 事前标准制定、事中过程监管与质量评估、事后质量提升的完整治理体系
  - 提供元数据管理、主索引管理、数据质量管理、数据服务管理、授权管理、安全管理、监控管理能力
