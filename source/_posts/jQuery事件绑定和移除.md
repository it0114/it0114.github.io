title: jQuery事件绑定和移除
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-05 23:30:00
---
# jQuery事件绑定
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            /*
            jQuery中有两种绑定事件的方式
            1.eventName(fn);
            编码效率略高因为有提示/ 部分事件jQuery没有实现，所以不能添加使用
            2.on(eventName,fn);
            编码效率略低因为没有提示/ 所有的js事件都可以添加 因为是使用字符串调用

            注意点:
            可以添加多个相同或者不同的事件 而且不会覆盖
            */
            // 第一种方式

            // $("button").click(function(){
            //   alert("hello Yam");
            // })

            // 第二种方式
            $("button").on("click", function () {
                alert("hello Yam1");
            })

        })
    </script>
</head>
<body>
<button>我是按钮</button>
</body>
</html>
```


# jQuery事件移除
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            $("button").click(text1);

            function text1() {
                alert("hello 1")
            }

            $("button").click(function () {
                alert("hello 2")
            });
            $("button").mouseenter(function () {
                alert("hello 3")
            });
            $("button").mouseleave(function () {
                alert("hello 4")
            });
            //off方法如果不传递参数，会移除所有的事件
            $("button").off();
            //off方法如果传递一个参数会移除指定类的事件
            $("button").off("click");
            //off方法如果传递两个参数，会移除指定类里面的指定函数
            $("button").off("click", text1);
        })
    </script>
</head>
<body>
<button>我是按钮</button>
</body>
</html>
```