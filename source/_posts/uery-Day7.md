title: jQuery-Day7
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-02-24 19:54:00
---
# scrolTop()方法
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .scroll{
            width: 100px;
            height: 200px;
            border: 1px solid #000;
            /*设置auto后，超出的部分会出现滚动条
            而如果是hidden的话超出部分就会隐藏起来*/
            overflow: auto;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            var btns = document.querySelectorAll("button");
            btns[0].onclick = function(){
                //获取滚动的偏移位
                console.log($(".scroll").scrollTop());
                //获取网页滚动的偏移位
                // 注意点:为了浏览器的兼容，需要按照如下的方式进行书写
                // body = ie
                // html = Google
                console.log($("body").scrollTop()+$("html").scrollTop());
            };
            btns[1].onclick = function(){
                //设置滚动的偏移位
                //$(".scroll").scrollTop(500);

                //设置网页滚动的偏移位
                // 注意点:为了浏览器的兼容，需要按照如下的方式进行书写
                $("html,body").scrollTop(500);
            };
            /*
            疑问:
            1.scrollTop()方法传承和不传参的区别？
                传参的话是设置，不传参的话是获取
            2.scrollTop()方法传参需要添加单位吗?
                不需要添加单位
            3.获取或设置整个网页滚动偏移需要注意什么
                浏览器兼容问题
            4.scrollTop()和scrollLeft()方法一样吗?
                操作都是一样的
            */
        })
    </script>
</head>
<body>
<div class="scroll">我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div我是div</div>
<button>获取</button>
<button>设置</button>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
</body>
</html>
```