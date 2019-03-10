title: jQuery命名空间和自定义事件
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-06 22:26:00
---
# jQuery命名空间
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
            /*
            命名空间是什么？
            1.用于多人开发的时候区分
            2.命名空间必须是使用on绑定事件
            3.要触发命名空间的事件必须使用trigger来触发
            */
            //命名空间使用
            // $(".son").on("click.yam",function(){
            //     alert("click1");
            // });
            // $(".son").trigger("click.yam");


            $(".son").on("click", function () {
                alert("click2");
            });
            /*
           命名空间事件冒泡注意点;
            利用trigger触发子元素带命名空间的事件，那么父元素带相同命名空间的事件也会被触发，而父元素没有命名空间的事件不会被触发
            利用trigger触发子元素不带命名空间的事件，那么子元素所有相同类型的事件和父元素所有相同类型都会被触发。 
          
            */
        });
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

# 关于命名空间的问题
1. 命名空间的作用是什么？
- 命名空间多用于来多人协作时候分辨出那个事件是谁写的
2. 命名空间的前提条件是什么
- 命名空间的前提条件是这个函数的绑定是用'on'进行绑定的



# jQuery自定义事件
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

            // $(".son").click(function (event) {
            //     alert("son");
            // });
            // $(".son").trigger("click");

            $(".son").on("myClick",function(){
               alert("son");
            });

            $(".son").trigger("myClick");

            //什么事自定义事件？
            //自定义事件就是创建一个系统没有的事件，并且让他响应我们的操作
            /*想要自定义事件。必须满足两个条件
                1.事件必须通过on绑定
                2.事件必须通过trigger来触发
            */
        });
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