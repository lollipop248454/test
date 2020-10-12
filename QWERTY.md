1.任务

Add a new vis function based on the open source spreadsheet codes:

https://github.com/myliang/x-spreadsheet

Report your experimental results, especially your gains and critical thinking.

# 2.实验方法与效果

首先下载开源源码到本地，然后根据index.html文件在此基础上进行添加与修改，并添加一个新的html页面vis.htm用于展示可视化结果。

1.利用load函数对表格中的数据进行初始化，设置大小，style以及交互式操作；

2.对于某一行某一列操作使用rows, cells来确定行与列，然后进行初始化数据，其中rows中的len用于初始化x-spreadsheet的行数。

3.对于定义的xs变量，有许多种操作，可以利用xs.getData()获取数据，利用xs.cell-selected()来选择特定的元素。

4.最后利用Windows中浏览器的window.localStorage来存储于获取数据，`localStorage` 中的键值对总是以字符串的形式存储，并且存储在 `localStorage` 的数据可以长期保留，直到手动删除，加上其属性属于只读，确保了数据的完整性以及正确性。



![image-20201012151819943](https://s1.ax1x.com/2020/10/12/0R8wnK.png)

![image-20201012152307299](https://s1.ax1x.com/2020/10/12/0R8oNQ.png)

# 部分关键代码

## index.htm

数据初始化：调用rows，cells，text，进行赋初值。

`      const rows = {
        len: 80,
        0:{
	cells:{
	0:{text: '10'},
	1 : { text: '20'},
	2:{text:'30'},
	3:{text:'40'},
	},
           },
        1:{
	cells:{
	0:{text: '20'},
	1 : {text: '30'},
	2:{text:'40'},
	3:{text:'10'},
	},
           }   
      };`      

数据存储至网页

`window.localStorage.data = data;
window.localStorage.r = r;
window.localStorage.l = l;
console.log(data,r,l);`

## vis.htm

数据获取，其中x-spreadsheet默认分隔符为，

`var data = window.localStorage.data.split(',');
var r = window.localStorage.r;
var l = window.localStorage.l;
console.log(data,r,l);`

数据转化：将数据转化为列表数组，然后方便进行D3操作，进行折线图的绘制。

`dd[i][j] = [j+1,data[g++]];`

利用两层镶嵌循环，将列表导入数组，即x,y值

然后利用D3将存储在列表数组里的数据可视化出来，部分关键代码

` 

        var linePath = d3.line()
                .x(function(d){console.log(d[0]);return xScale(d[0]);})
                .y(function(d){console.log(d[1]);return yScale(d[1]);});
        var colors = [d3.rgb(0,0,255),d3.rgb(0,255,0),d3.rgb(255,0,0)];
        svg.selectAll("path")
            .data(dd)
            .enter()
            .append("path")
            .attr("transform","translate(" +padding.left +","+padding.top +")")
            .attr("d",function(d){
            return linePath(d);
            })
            .attr("fill","none")
            .attr("stroke-width",3)
            .attr("stroke",function(d,i){
                return colors[i];
            });
        svg.append("g")
            .attr("class","axis")
            .attr("transform","translate("+padding.right+","+(height-padding.bottom)+")")
            .call(xAxis);`
            svg.append("g")
                .attr("class","axis")           .attr("transform","translate("+padding.left+","+padding.top+")")
                .call(yAxis);

# 实验收获

1.了解了x-spreadsheet的一些基本操作，如何进行初始化，如何调用获取函数，如何进行页面转化，如何利用x-spreadsheet在网页上与用户进行交互式操作，如何利用浏览器将网页中的数据进行存储于获取；

2.加深了D3的印象，能够更加熟练的运用D3对不同的数据类型，不同的数据格式，进行多种可视化操作；

3.对js与html的编写有了更深一步的了解，增强了自己的写代码能力以及debug能力。

# 批判性思考

优点：

x-spreadsheet是一款基于js开发的，简单的易用的在线表格插件，易于使用并且可操作性强，灵活性高，能够快速的启动，可读性强，能够立刻找到自己想要的数据信息。

缺点：

1.相比数据库而言需要等待的时间太长了

2.无法打开较大的电子表格

3.只能通过复制粘贴来进行过滤操作

