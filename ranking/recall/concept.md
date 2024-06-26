# Recall

## Approaches

1. 经典搜索召回
   1. 倒排索引
2. 电商搜索召回
   1. 文本召回
      1. 流程: 倒排索引 + 正排索引
      2. 问题: 召回能力不足
      3. 解决: 扩召回
         1. query 扩写
         2. item 扩写
   2. 结构化召回
      1. 通过 query 解析出的结构化 id 索引与物料 item 的 id 索引匹配
   3. 个性化召回
      1. 特征: 利用用户商品交互序列召回
      2. 分类
         1. q2i2i: 根据 query 历史曝光点击 item 召回
         2. u2i2i: 根据 user 历史曝光点击 item 召回
         3. u2s2i: 根据 user 偏好的 seller 历史曝光点击 item 召回
   4. 向量召回
      1. 特征: 基于 query-doc pair 的语义相似性召回
      2. 方法: 深度语义匹配模型 (双塔模型)
      3. 训练: 正负样本对比学习
