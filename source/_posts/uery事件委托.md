title: jQuery事件委托
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-07 23:30:00
---
# jQuery事件委托

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <script src='js/jquery-1.12.4.js'></script>
    <script>
        $(function () {
            //开始编写jQuery代码
            //什么是事件委托？
            //事件委托就是请别人帮忙办事情，然后把办好的事情的结果反馈给我们


            $("button").on("click", function () {
                $("ul").append("<li>我是新增的li</li>");
            });


            //在jquery中，如果通过核心函数找到的元素不止一个，那么在添加事件的时候，jquery会遍历找到的元素，给所有的元素添加事件

            // $("ul>li").click(function(){
            //     console.log($(this).html());
            // });
            //利用事件委托来实现监听所有的li
            $("ul").delegate("li", "click", function () {
                console.log($(this).html());
            })

            // this为什么会指向li呢？因为事件冒泡，li冒泡给了父级ul，ul接收到的冒泡就是li发出的 ，所以this是li
        });
    </script>
</head>
<body>
<ul>
    <li>我是第1个li</li>
    <li>我是第2个li</li>
    <li>我是第3个li</li>
</ul>
<button>新增一个li</button>
</body>
</html>
```

# 事件委托小练习
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

        html, body {
            width: 100%;
            height: 100%;
        }

        .mask {
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            position: fixed;
            top: 0;
            left: 0;
        }

        .login {
            width: 522px;
            height: 290px;
            margin: 100px auto;
            position: relative;
        }

        .login > span {
            width: 50px;
            height: 50px;
            /*background: red;*/
            position: absolute;
            top: 0;
            right: 0;

        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            $("a").click(function () {

                var $mask = $("<div class=\"mask\">\n" +
                    "    <div class=\"login\">\n" +
                    "        <img src=\"images/login.png\" alt=\"\">\n" +
                    "        <span></span>\n" +
                    "    </div>\n" +
                    "</div>");

                $("body").append($mask);

                $("body").delegate(".login>span", "click", function () {
                    $mask.remove();
                });
                return false;
            })
        })
    </script>
</head>
<body>

<!--<div class="mask">-->
<!--<div class="login">-->
<!--<img src="images/login.png" alt="">-->
<!--<span></span>-->
<!--</div>-->
<!--</div>-->

<a href="https://www.it0114.xyz">点击登录</a>
<br>
<br>

<div>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolore esse laudantium quisquam ullam. Amet est harum iste, labore laborum porro quibusdam tempora vitae voluptas voluptatibus? Amet eum minus nesciunt?
</div>
</body>
</html>

```