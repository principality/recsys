# 业绩案例

唯品会海量实时OLAP分析技术升级之路
http://www.yunweipai.com/archives/21724.html

# Cost-based optimization

使用CBO后，hive可以胜任ad-hoc查询

- tez:
  - 减少mapper/reduce落盘的代价
  - 逻辑优化算法
    - Projection Pruning
    - Deducing Transitive Predicates
    - Predicate Push down
    - Merging of Select-Select, Filter-Filter in to single operator
    - Multi-way Join
    - Query Rewrite to accommodate for Join skew on some column values
  - 物理优化算法
    - Partition Pruning
    - Scan pruning based on partitions and bucketing
    - Scan pruning if query is based on sampling
    - Apply Group By on the map side in some cases
    - Perform Join on the Mapper
    - Optimize Union so that union can be performed on map side only
    - Decide which table to stream last, based on user hint, in a multi way join
    - Remove unnecessary reduce sink operators
    - For queries with limit clause, reduce the number of files that needs to be scanned for the table.
    - For queries with Limit clause, restrict the output coming from mapper by restricting what Reduce Sink operator generates.
    - Reduce the number of Tez jobs needed for answering user submitted SQL query
    - Avoid Map-Reduce jobs in case of simple fetch query
    - For simple fetch queries with aggregation, perform aggregation without Map-Reduce tasks
    - Rewrite Group By Query to use index table instead of original table
    - Use Index scans when predicates above table scan is equality predicates and columns in predicate have indexes on it.
- calcite
  - 基于成本的规则优化器（需要元数据），>50条优化规则（自动生成HINTS）
  - join排序和join算法，难以从CBO获得提升
  - 使用calcite可以重排DAG执行次序，以查询响应速度为排序

# LLAP
