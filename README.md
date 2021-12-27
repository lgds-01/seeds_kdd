# 聚类分析之种子数据集

## 数据集
数据集采用[UCI的Seeds Data Set](http://archive.ics.uci.edu/ml/datasets/seeds#)（关于小麦品种的籽粒数据集）其中包含210条数据，每条数据由7个属性外加1个类别组成，数据集总共分为3类。

七个属性分别如下：

1. 面积 A
2. 周长 P
3. 紧密度 $C = 4*pi*A/P^2$
4. 籽粒长度
5. 籽粒宽度
6. 不对称系数
7. 仁槽长度

## 目的
本项目是数据挖掘课程的大作业，主要目的是利用聚类算法将种子数据集进行聚类分析。本项目使用了K-Means算法及K-Means++算法对数据集进行聚类分析，并利用可视化和ARI评估了聚类结果的优劣

## 思考
1. 根据数据集真实标签产生的可视化图像可知，数据集虽然有较为明显的三个聚类分布，但聚类之间有部分重合，因此对于聚类算法的结果与真实结果可能有较大偏差。两个算法的ARI结果都在0.7左右，验证了这一点。
2. K-Means++主要是为了改进K-Means随机选择初始可能导致陷入局部最优的情况，而这种情况在此次聚类中并没有出现，因此两个算法的结果表现出一定的相似性
3. 此数据集有7个属性，而这7个属性之间有一定的重复，如籽粒长度、籽粒宽度和面积，并且不同属性对于不同类的增益程度不同，因此可以考虑对属性乘以权重（用于突出不同属性对不同类的重要程度/增益效果）
