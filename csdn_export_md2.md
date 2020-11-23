## WEEK-11
#### 1.服务器配置

进入控制台，点击云数据库 RDS，点击实例列表（若实例列表空则切换右上角地区）
点击管理-账号管理，创建管理员账号，（切换为 高权限账号）
点击-数据安全性-白名单设置-将默认 ip 段改为 0.0.0.0/0
![配置完成](https://img-blog.csdnimg.cn/20201123114358826.png#pic_center)

#### 记录外网IP地址

![配置完成后](https://img-blog.csdnimg.cn/20201122224914608.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l3cWR5,size_16,color_FFFFFF,t_70#pic_center)

#### 2.在手机中下载AWARE并安装

![image-20201123142322147](https://img-blog.csdnimg.cn/20201123142800251.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hleGlhbmdxaW4=,size_16,color_FFFFFF,t_70#pic_center)

#### 3.连接aware与云服务器

打开网址https://api.awareframework.com/index.php/auth
登录谷歌账号
将study database修改为 Remote server
hostname为外网IP地址
port默认为3306
database为自己创建的数据库名称
username为配置服务器时创建的管理员账号
password为管理员账号密码
如果显示connection success！则连接成功
![连接成功](https://img-blog.csdnimg.cn/20201123114056552.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l3cWR5,size_16,color_FFFFFF,t_70#pic_center)

#### 4.aware上扫码加入，将数据传到阿里云上，为后续可视化收集数据

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201123114607594.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l3cWR5,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201123114607585.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3l3cWR5,size_16,color_FFFFFF,t_70#pic_center)

