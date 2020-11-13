# 数据集使用

用到了手写数字数据集（10992个样本），分别是从0到9的手写体

# 实验过程

### 1.KNN

直接Python调库，将训练数据拆分为训练集与测试集，利用训练集对模型进行训练，利用测试集进行accuracy与f1-score的求解。通过调整KNN的邻居个数，发现4个邻居时效果最好，解得正确率以及f1-score为

![img](https://img-blog.csdnimg.cn/20201113220016317.png#pic_center)

### 2.逻辑回归

数据处理同上，逻辑回归不同调参，直接训练数据即可，解得正确率以及f1-score为

![image-20201113195332529](C:\Users\棒棒糖\AppData\Roaming\Typora\typora-user-images\image-20201113195332529.png)

### 3.利用NHST进行假设检验

将测试集均分为50份，分别求出50个accuracy以及f1-score，然后对他们进行假设检验，结果分别为

![image-20201113200118000](C:\Users\棒棒糖\AppData\Roaming\Typora\typora-user-images\image-20201113200118000.png)

![image-20201113200301018](C:\Users\棒棒糖\AppData\Roaming\Typora\typora-user-images\image-20201113200301018.png)

其p值都极小，且小于0.05，可见两者的accuracy与f1-score不能认为相等，两者的分类效果有区别。相比而言KNN更好。 
