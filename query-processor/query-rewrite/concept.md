# Query Rewrite

## Standard Procedure

1. 如果 Query 分词后直接命中 Term 倒排索引, 则直接出发 Doc 召回
2. 如果 Query 分词空命中或少命中, 则触发多粒度分词, 词向量匹配, Query 改写

## Popular Techniques

1. Query 归一: 对 Query 进行特殊字符处理, 如大小写转换, 去除标点符号, 去除停用词
2. Query 纠错: 对 Query 进行拼写纠错, 避免误召回
3. Query 丢词: 对空召回, 少召回的 Query 进行非关键词的丢弃, 进行二次召回
4. Query 拓展: 对 Query 进行语义上的拓展

## Query Extension

### Procedures

1. Query 改写候选召回
2. Query 判别

### Techniques

1. Query 改写候选召回
   1. 基于同义词: 同义词表映射
   2. 基于统计: 用户行为统计, 如 i2i (协同过滤方式), q2i (swing 算法)
      1. 缺点: 对于用户行为不足的长尾 Query, 改写不够准确
   3. 基于内容
      1. 分类
         1. 基于语义匹配
            1. 模型: 深度语义匹配模型 (双塔模型)
            2. 数据
               1. 直接来源: 基于行为统计产生的 <query, query> pair
               2. 间接来源: 由 <query, item> pair 间接生成的 <query, query> pair
         2. 基于生成
            1. 模型: seq2seq 模型
            2. 数据:
               1. 直接来源: 基于行为统计产生的 <query, query> pair
               2. 间接来源: 由 <query, item> pair 生成的 <query, query> pair
      2. 优点
         1. 对于头部 Query 的语义内容的理解可以泛化到长尾 Query
   4. 基于 Session
      1. 假设
         1. 用户在同一个 Session 中的搜索意图基本相近
         2. 位于相似上下文中的 Query 语义相近
      2. 方法
         1. Session 假设下, 通过频率统计即可
         2. Context 假设下, 可以训练 word2vec 模型, 或者使用 seq2seq 生成式模型
2. Query 改写判别
   1. 方法:
      1. LR 逻辑回归
      2. GBDT 特征融合
      3. DNN 深度神经网络
