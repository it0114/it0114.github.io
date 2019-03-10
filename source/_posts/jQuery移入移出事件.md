title: jQuery移入移出事件
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-08 01:08:00
---
# jQuery移入移出事件
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
        .father{
            width: 200px;
            height: 200px;
            background: red;
        }
        .son{
            width: 100px;
            height: 100px;
            background: skyblue;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            //方法1

            // jquery移入事件
            // $(".father").mouseover(function(){
            //     console.log("father被移入了");
            // })
            // //jquery移出事件
            // $(".father").mouseout(function(){
            //     console.log("father被移出了");
            // })

            //注意点:
                //使用这个方法，如果你进入father中的son他就会多次触发移入移出，所以这个方法并不好

            //方法2
            // $(".father").mouseenter(function(){
            //     console.log("father被移入了");
            // })
            // $(".father").mouseleave(function() {
            //     console.log("father被移出了");
            // })

            //注意点:
            //这个办法的话 是比较完善的 进入他的子元素是不会再影响移入移出的，推荐使用

            // 方法3

            $(".father").hover(function(){
                console.log("father被移入了");  //监听移入事件
            },function(){
                console.log("father被移出了");  //监听移出事件
            })
            
            // 注意点
                //这个方法就是结合了方法2的好处，而且写的代码更加的少了，他的传参位置可以穿一个参数，也可以传两个参数，如果只传一个function的话，那么只 监听移入事件。
        })
    </script>
</head>
<body>

<div class="father">
    <div class="son"></div>
</div>
</body>
</html>
```