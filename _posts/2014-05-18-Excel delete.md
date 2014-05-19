---
date: 2014-05-18 00:25:22+00:00
layout: post
title: Excel 筛选删除
thread: 143
categories: 技术
---
<!-- ###Excel 删除不必要信息			
步骤如下  >首先我的Office是2007版本的，打开你要筛选删除的Excel表，以下图为例：		
> 1.用鼠标点到你要筛选的那一列其中你要选中的例如本例中的“李四”，再点击开始栏里边即Excel表右上角的*排序和筛选*图标并选中其中的*筛选*![Step 1](/assets/Delete_1.jpg)		
>2.点击本例选中的_李四_那格右下方按钮，点击全选，再把_李四_打勾处去掉，确认。![Step 2](/assets/Delete_2.jpg)		
>3.跳转回Excel表后选中要删除的内容。![Step 3](/assets/Delete_3.jpg)		
>4.回到Excel表后再次点击*李四*![Step 4](/assets/Delete_4.jpg)右下方的按钮，点击筛选，选中“李四”并确定，![Step 5](/assets/Delete_5.jpg)		最后就得到了（删除了不要的信息）![Step 6](/assets/Delete_6.jpg)	 -->		##html页面显示时间
方法一：
html代码：

    <body>  
    <div id="time"></div>  
	   <script type="text/javascript">  
		change();  
		function change()  
		{  
    	   var today;  
    	   today = new Date();  
     	   timeString = today.toLocaleString();  
     	   document.getElementById("time").innerHTML = timeString;  
     	   setTimeout("change();", 1000);  
		}  
	   </script>  
    </body> 

方法二(在onload中调用setInterval)：
    
    <body onload="setInterval('change()',1000)">  
        <div id="time">  </div>  
      	<script type="text/javascript">  
             function change()  
             {  
                  var today;  
                  today = new Date();  
                  timeString = today.toLocaleString();  
                  document.getElementById("time").innerHTML = timeString;  
            }  
          </script>  
    </body>  

方法三：

    <body onload="show();">  
        <div id="nowDiv"></div>           
        <script type="text/javascript">  
            function show()
            {                  
                var date = new Date();  
                var now = "";                  
                now = date.getFullYear()+"年";  
                 if(date.getMonth() < 10)  
                  {  
                       nownow = now +"0";  
                    }  
                nownow = now + (date.getMonth()+1)+"月";   
                 //取月的时候取的是当前月-1如果想取当前月+1就可以了                  
          
                  if(date.getDate() < 10)  
                    {  
                       nownow = now +"0";  
                    }  
                nownow = now + date.getDate()+"日  ";     
                if(date.getHours() < 10)  
                   {  
                       nownow = now +"0";  
                   }  
                nownow = now + date.getHours()+":";     
                if(date.getMinutes() < 10)  
                    {  
                       nownow = now +"0";  
                       }  
                nownow = now + date.getMinutes()+":";  
          
                if(date.getSeconds() < 10)  
                    {  
                        nownow = now +"0";  
                    }  
                 nownow = now + date.getSeconds()+" ";  
                document.getElementById("nowDiv").innerHTML = now;   
             //div的html是now这个字符串                  
               setTimeout("show()",1000);   
            //设置过1000毫秒就是1秒，调用show方法                  
            }  
        </script>  
    </body> 