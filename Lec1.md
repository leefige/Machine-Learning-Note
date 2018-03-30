# Lecture 1 - 3/2

## open office hour
16:30 - 17:30 Mon

## 一个核心
特征>算法

## 参考书
1. 机器学习 TOM MITCHELL
2. 机器学习导论
3. 机器学习 周志华

## topics
### 初级话题
1. 决策树
2. 贝叶斯
3. 隐马尔科夫
4. KNN
5. SVM：没有好想法时，试试SVM，不会太差
6. 无监督&聚类

### 高级话题
7. 图
8. ensemble learning：一般优于单一
9. deep learning
10. transfer learning
11. 缺失参数：EM

### 理论
12. 评估 / PAC-可能近似学习 

### NOT involved
- NN
- 遗传
- probabilistic graph...

## 考核
- 3 * hw：20%
- 2 * 实验：40%
- proj / 考试：40%
    - proj要有背景
    - 如何搜集数据
    - 用什么方法
    - 评价指标

---

## TOPIC 1: 什么是机器学习

### 应用背景
- 数据挖掘：应用场景
- business intelligence
    - P&G：商品放在视线上下
- 信用卡risk分析
- 电子邮件过滤：SPAM，贝叶斯学习
- 推荐算法：新闻、amazon
- 无人驾驶：NN，4 layer
- 搜索引擎

### what's machine learning
- 司马贺：学习：系统的变化，使得下次完成相同任务时更有效率
- Michalski：学习：对已有经验的表示的构造/修改
- Mitchell：基于经验对任务的改进
- 总结：
    1. Task
    2. Experience
    3. Performance：对性能的改进

### 系统设计——training experience
- training experience是否对目标有代表性？
- 未预期到的结果——对训练数据的要求
    - 数据集的bias（香蕉/月亮）
    - 顺序：数字识别，若按0~9训练，则最后只能识别9——应该打乱
    - category相关的meta信息（对信息本身的描述的信息）
    - 【关键】data bias: data, procedure, features...