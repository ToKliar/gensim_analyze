# Gensim分析

对自然语言处理库Gensim的分析

## 任务要求

本仓库对于Gensim的分析基于翻译技术与实践课程中的作业，作业的要求如下：

基础任务：知道它是啥，能做什么

进阶任务：了解其所有可能的用途，跑通部分测试用例

## Gensim介绍

Gensim是一款开源的第三方Python工具包，用于从原始的非结构化的文本中，无监督地学习到文本隐层的主题向量表达。  

它支持包括TF-IDF，LSA，LDA，和word2vec在内的多种无监督的主题模型算法，支持流式训练，并提供了诸如相似度计算，信息检索等一些常用任务的API接口

本项目对gensim库的各个功能进行介绍和简单的使用

参考资料：
+ https://www.geeksforgeeks.org/nlp-gensim-tutorial-complete-guide-for-beginners/
+ Gensim中文文档 https://gensim.apachecn.org/#/
+ Gensim官方文档 https://radimrehurek.com/gensim/auto_examples/index.html#documentation
+ 15分钟入门Gensim https://zhuanlan.zhihu.com/p/37175253

## Gensim功能

Gensim的主要功能有：
+ **内存独立性**：任何时候都不需要整个训练语料库完全存放在内存中，因此可以处理大型的Web级语料库
+ **内存共享**：经过训练的模型可以持久保存并通过mmap加载，多个进程可以共享数据从而减少内存占用
+ **向量空间算法的高效实现**：包括Word2Vec、Doc2Vec、FastText、Tf-Idf、潜在语义分析（LSI，LSA）、隐含狄利克雷分布（LDA）和随机投影（RP）
+ 对主流数据格式的I/O包装和读写
+ 通过语义表示对文档进行相似性查询

## Gensim的核心概念

### 语料Corpus

文本文档的集合

Corpus在Gensim中有两种作用
1. 作为模型训练的输入，模型通过训练语料查找文档的主题，初始化模型的参数
2. 根据训练后的主题模型从文档中提取主题，通过语义相似性、聚类等方式索引语料库

### 向量Vector

用数学方式表达文档，将文档转换为一串数字  

比如：可以用词袋模型将文档表示为向量，每个向量包含字典中每个单词在该文档中的频率

通常情况下，向量中包含很多零值，为了减少内存占用，Gensim可以省略向量中所有值为0的元素，用稀疏向量（Sparse Vector）的格式表示文档。  
如：(0.0, 2.0, 5.0) -> [(2, 2.0), (3, 5.0)]

### 模型 Model

模型指将文档从一种表示形式转换到另一种文档表示。  
在Gensim中文档通过向量表示，模型可以被认为是将向量从一种表示形式转换为另一种表示形式的算法

Gensim实现了Word2Vec、LsiModel、LdaModel等模型


