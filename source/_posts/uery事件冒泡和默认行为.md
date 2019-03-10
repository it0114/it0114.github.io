title: jQuery事件冒泡和默认行为
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-05 23:32:00
---
# jQuery事件冒泡和默认行为
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        .father {
            width: 200px;
            height: 200px;
            background: red;
        }

        .son {
            width: 100px;
            height: 100px;
            background: skyblue;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            //  1.什么是事件冒泡？
            //如果给子元素和父元素都注册了点击事件，子元素在响应事件的时候父元素也会跟着响应事件。这就是事件冒泡
            //  2.如何阻止事件冒泡
            // 1.给子元素添加 return false
            // 2.给子元素的函数加 event 然后调用 event.stopPropagation();
            //  3.什么事默认行为？
            //例如点击跳转，你没有给事件，但是他也跳转了 ，这个就是默认行为
            //  4.如何阻止默认行为
            // 1.给元素添加 return false;
            // 2.给元素添加  event.preventDefault();

            //
            /* 事件冒泡
            $(".son").click(function(event){
                alert("son");
                return false;           //阻止事件冒泡
                // event.stopImmediatePropagation();  //阻止事件冒泡
            });

            $(".father").click(function(){
                alert("father");
            });
            */

            /*阻止默认事件*/
            $("form").click(function (event) {
                alert("尝试一下打开 https://www.it0114.xyz");
                // return false;           //阻止默认事件
                event.preventDefault();     //阻止默认事件
            })
        })
    </script>
</head>
<body>
<div class="father">
    <div class="son"></div>
</div>
<a href="https://www.it0114.xyz">我是Yam</a>
<form action="https://www.taobao.com">
    <input type="text">
    <input type="submit">
</form>
</body>
</html>
```