title: jQuery-Day5
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-02-22 19:27:00
---
# 操作类
#### 1.addClass(class|fn)
>用:添加一个类
如果要添加多个类，多个类名之间用空格隔开



#### 2.removeClass([class|fn])
>作用:删除一个类
如果要添加多个类，多个类名之间用空格隔开



#### 3.toggleClass(class|fn[sw])
>作用：切换类
切换就是，有就删除，没有就添加

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
        .class1{
            width: 100px;
            height: 100px;
            background: red;
        }
        .class2{
            border: 10px solid #000;
        }

    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
           
            var btns = document.getElementsByTagName("button");
            btns[0].onclick =function(){
                // 添加一个类名
                // $("div").addClass("class1");
                //添加多个类名
                $("div").addClass("class1 class2");
            };
            btns[1].onclick =function(){
                //删除一个class
                $("div").removeClass("class2")
                //删除多个class
                // $("div").removeClass("class1 class2")
            };
            btns[2].onclick =function(){
                //切换类
                console.log($("div").toggleClass("class2"));
            }
        })
    </script>
</head>
<body>

<button>添加类</button>
<button>删除类</button>
<button>切换类</button>
<div></div>

</body>
</html>

```
# jQuery文本值相关方法

#### 1.html([val|fn])
>和原生js中的innerHTML一模一样
#### 2.text([val|fn])
>和原生js中的innerText一模一样
#### 3.val([val|fn|arr])

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

        div {
            width: 100px;
            height: 100px;
            border: 1px solid #000;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            /*
            1.html([val|fn])
            和原生js中的innerHTML一模一样
            2.text([val|fn])
            和原生js中的innerText一模一样
            3.val([val|fn|arr])
            */
            var btns = document.getElementsByTagName("button");
            btns[0].onclick = function () {
                //设置html
                $("div").html("<p>我是段落<span>我是span</span></p>")
            };
            btns[1].onclick = function () {
                //获取html
                console.log($("div").html());
            };
            btns[2].onclick = function () {
                //设置text
                $("div").text("我设置了text")
            };
            btns[3].onclick = function () {
                //获取text
                console.log($("div").text());
            };
            btns[4].onclick = function () {
                //设置value
                $("input").val("请输入内容");
            };
            btns[5].onclick = function () {
                //获取value
                $("input").val();
            }
        })
    </script>
</head>
<body>
<button>设置html</button>
<button>获取html</button>
<button>设置text</button>
<button>获取text</button>
<button>设置value</button>
<button>获取value</button>
<div></div>
<input type="text">
</body>
</html>
```


