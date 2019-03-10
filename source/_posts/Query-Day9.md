title: jQuery-Day9
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-02-28 20:54:00
---
# 操作样式和类

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        .black {
            background: #000;
            color: #fff;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            var a = $(".a")
                .addClass("black") //增加类名
                .removeClass("b") //删除类名
            ;

            console.log(a.hasClass("black"));//检测是否有class，返回布尔

            a.hide();//显示元素
            a.show();//隐藏元素

            a.fadeOut();//带动画的隐藏 可传参数单位为毫秒
            a.fadeIn();//带动画的显示 可传参数单位为毫秒

            a.slideUp();//带动画的向上隐藏 可传参数单位为毫秒
            a.slideDown();//带动画的向下隐藏 可传参数单位为毫秒


        })
    </script>
</head>
<body>
<div class="a b">A</div>
</body>
</html>
```

# 小练习
```javascript
	<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        #board.active {
            color: red;
        }

        #board {
            background: #000;
            display: inline-block;
            padding: 5px;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码

            var board = $("#board");

            function toggle() {
                if (board.hasClass("active")) {
                    board.removeClass("active");
                }
                else {
                    board.addClass("active");
                }
            }

            setInterval(toggle, 200);

        })
    </script>
</head>
<body>
<div id="board">保健用品 二楼左转</div>

</body>
</html>
```