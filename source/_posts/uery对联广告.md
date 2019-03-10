title: jQuery对联广告
toc: true
author: Yam
tags:
  - jQuery
categories: []
date: 2019-03-10 22:21:00
---
# jquery对联广告
```javascript

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>40-对联广告</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .left{
            float: left;
            position: fixed;
            left: 0;
            top: 200px;
        }
        .right{
            float: right;
            position: fixed;
            right: 0;
            top: 200px;
        }
        img{
            display: none;
        }
    </style>
    <script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.js"></script>
    <script>
        $(function () {
            // 1.监听网页的滚动
            $(window).scroll(function () {
                // 1.1获取网页滚动的偏移位
                var offset = $("html,body").scrollTop();
                // 1.2判断网页是否滚动到了指定的位置
                if(offset >= 500){
                    // 1.3显示广告
                    $("img").show(1000);
                }else{
                    // 1.4隐藏广告
                    $("img").hide(1000);
                }
            });
        });
    </script>
</head>
<body>
<img src="images/left_ad.png" class="left">
<img src="images/right_ad.png" class="right">
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
</body>
</html>
```