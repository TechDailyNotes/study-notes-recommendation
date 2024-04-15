# Serial Recommendation System

## Why SRS?

1. 用户商品的交互是序列化的
2. 用户的喜好和商品的流行度是动态变化的
3. 用户商品的交互序列是在上下文中发生的

## Challenges

1. 处理长的用户商品交互序列
   1. 高阶依赖关系
   2. 长期依赖关系
2. 以灵活的顺序处理用户商品交互序列
   1. 点式依赖
   2. 集合依赖
3. 处理带有噪声的用户商品交互序列
4. 处理带有异构关系的用户商品交互序列
5. 以层级结构方式处理用户商品交互序列
   1. 元数据与用户商品交互序列
   2. 子序列与用户商品交互序列

## Approaches

1. Traditional Sequence Models
   1. Sequential Pattern Mining
   2. Markov Chain Models
2. Latent Representation Models
   1. Factorization Machines
   2. Embedding Models
3. Deep Neural Networks
   1. Basic DNN
      1. RNN
      2. CNN
      3. GNN
   2. Advanced Models
      1. Attention Models
      2. Memory Models
      3. Mixture Models
