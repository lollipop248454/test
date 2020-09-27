# 有关数据质量的讨论

https://wenku.baidu.com/view/458e7f3649649b6648d747f7.html#

数据质量的重要性：

数据是连接现实世界和虚拟世界的桥梁，如果数据质量出现问题，无法反映现实世界的状况，那么建立起来的虚拟模型就会有较大的偏差，从而预测出有偏差甚至完全相反的结果，如果是一个企业对于未来市场的判断，那么这种后果将是极其严重的，传统数据的重要性不言而喻。

常见的数据质量问题有：

数据真实性

数据准确性

数据唯一性

数据完整性

数据一致性

数据关联性

数据及时性

OpenRefine 操作简介博客：

https://blog.csdn.net/zw0Pi8G5C1x/article/details/86486324

# 数据清洗

初始数据：

![img](file:///C:\TEMP\ksohtml5768\wps1.jpg) 

其中日期列直接用日期格式就会如上图所示添加了很多不需要的时间信息。执行以下操作变换时间格式：

（1）将所有列改为同一种日期格式，改完如图中绿色部分。

![img](file:///C:\TEMP\ksohtml5768\wps2.jpg) 

（2）将日期模式改为文本格式，去掉不相关的信息

![img](file:///C:\TEMP\ksohtml5768\wps3.jpg) 

（3）最终效果图：

![img](file:///C:\TEMP\ksohtml5768\wps4.jpg) 

匹配日期格式：日期按照xxxx-xx-xx表示，将匹配条件倒置即可匹配到不合要求的日期格式，将不匹配的行删去

![img](file:///C:\TEMP\ksohtml5768\wps5.jpg) 

![img](file:///C:\TEMP\ksohtml5768\wps6.jpg) 

 

匹配性别：别只能为男或者女，将匹配条件倒置可以看见不被匹配的行的原因是性别栏为否，将不匹配的行删除。

![img](file:///C:\TEMP\ksohtml5768\wps7.jpg) 

![img](file:///C:\TEMP\ksohtml5768\wps8.jpg) 

匹配姓名：姓名只能为中文字符，通过匹配发现有1行没被匹配，倒置发现该行数据缺失，将其删除。

![img](file:///C:\TEMP\ksohtml5768\wps9.jpg) 

 

![img](file:///C:\TEMP\ksohtml5768\wps10.jpg) 

匹配学号：基本要求是12位数字，直接用正则表达式匹配，倒置不符合要求的13位数字删除。

![img](file:///C:\TEMP\ksohtml5768\wps11.jpg) 

费用的基本要求肯定是要大于等于0 的，因此用正则表达式将小于0的数字所在行删除。

![img](file:///C:\TEMP\ksohtml5768\wps12.jpg) 

通过删除，最终结果是3行。

![img](file:///C:\TEMP\ksohtml5768\wps13.jpg)



最后利用OpenRefine的导出功能导出自己想要的文件格式即可

![image-20200927212237366](C:\Users\棒棒糖\AppData\Roaming\Typora\typora-user-images\image-20200927212237366.png)