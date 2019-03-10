title: jQuery-Day6
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-02-23 16:04:00
---
# 操作样式方法
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
            // 1.逐个设置
            $("div").css("width", "100px");
            $("div").css("height", "100px");
            $("div").css("background", "red");
            // 2.链式设置
            // 注意点:链式操作如果大于3步，建议分开，不然阅读性会很差
            $("div").css("width", "100px").css("height", "100px").css("background", "blue")
            // 3.批量设置(推荐使用)
            $("div").css({
                width: "100px",
                height: "100px",
                background: "yellow"
            })
            // 4.获取css样式值
            //获取用console.log打印出来
            console.log($("div").css("background"));
        })

        //jquery中如果想用-号的属性，例如background-color那么有以下两种写法
        $("div").css({
           //backgroundColor: "red", //驼峰命名法
           //"background-color":"red" //直接把他当字符串使用 
        })

    </script>
</head>
<body>

<div></div>

</body>
</html>
```

# jQuery尺寸和位置操作

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        *{
            margin: 0;
            padding:0;
        }
        .father{
            width: 200px;
            height: 200px;
            background: red;
            border: 50px solid #000;
            margin-left: 50px;
            position: relative;

        }
        .son{
            width: 100px;
            height: 100px;
            background: blue;
            position: absolute;
            left: 50px;
            top: 50px;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            var btns = document.getElementsByTagName("button");
            //监听获取
            btns[0].onclick = function(){
                //获取元素的宽度
                //.log($(".father").width());
                //获取innerWidth
                //console.log($(".father").innerWidth());
                //console.log($(".father").innerHeight());
                //获取outerHeight
                //console.log($(".father").outerHeight());

                //offset()
                //作用:获取元素距离窗口的偏移位
                //console.log($(".son").offset().left);
                //position()
                //作用:获取元素距离定位元素的偏移位
                //console.log($(".son").position().top);

            };
            //监听设置
            btns[1].onclick = function(){
                //设置元素的宽度
                //$(".son").width("500px");
                //设置innerWidth
                //$(".father").innerHeight("50px");
                //$(".father").outerHeight("800px");

                //offset()
                // 设置元素距离窗口的偏移量
                //$(".son").offset({
                //    left: 10
                //})

                //position()
                //作用:设置元素距离定位元素的偏移位
                // 注意点:position方法只能获取，不能设置，设置的方法有太多了，例如css都可以

            }
        })
    </script>
</head>
<body>
<div class="father">
    <div class="son"></div>
</div>
<button>获取</button>
<button>设置</button>
</body>
</html>
```