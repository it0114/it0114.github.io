title: jQuery-tab选项卡
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-09 22:40:00
---
# tab选项卡
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
            list-style: none;
        }

        .box {
            width: 440px;
            height: 298px;
            margin: 100px auto;
            border: 1px solid #000;
        }

        .nav {
            width: 100%;
        }

        .nav > li {
            width: 110px;
            height: 50px;
            background: skyblue;
            float: left;
            text-align: center;
            line-height: 50px;
            color: #000;
            cursor: pointer;
        }

        .nav .current {
            background: orange;
        }

        img {
            vertical-align: top;
        }

        .content li {
            display: none;
        }

        .content .show {
            display: block;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码

            $(".nav>li").hover(function () {
                $(".nav>li").removeClass("current");    //删除所有的class
                $(this).addClass("current");            //给选中的li添加class
                var index = $(this).index();            //选出li所在的索引
                var $li = $(".content>li").eq(index);   //让要显示的加上class
                $li.siblings().removeClass("show");   //删除所有图片的class
                $li.addClass("show");

                //eq就是在一堆元素中找出指定的哪个，并且包装成jQuery对象返回
                //get方法是一样的 但是不会包装成jQuery返回
                // index就是找到索引值
                //siblings()选中兄弟节点中非当前的其他选项

            })
        })
    </script>
</head>
<body>
<div class="box">
    <ul class="nav">
        <li class="current">HTML5</li>
        <li>jQuery</li>
        <li>C语言</li>
        <li>GO语言</li>
    </ul>
    <ul class="content">
        <li class="show"><img src="images/11.jpg" alt=""></li>
        <li><img src="images/12.jpg" alt=""></li>
        <li><img src="images/13.jpg" alt=""></li>
        <li><img src="images/14.jpg" alt=""></li>
    </ul>
</div>
</body>
</html>
```