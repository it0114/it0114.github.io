title: jQuery-Day10
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-02 15:01:00
---
# 操作样式
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
            //获取一个text元素

                    // var text = $("#a").text();
                    //console.log(text);

            //改变一个text元素

                    //$("#a").text("text");

            //获取一个html元素

                    // var html = $("#a").html();
                    // console.log(html);

            //改变一个html元素
            //直接改变内容

                    // $("#a").html("html");

            //更改标签
                    // $("#a").html("<div>html</div>")

            //text和html的区别
            /*
                    text会改变元素里面的内容 但是不会改变标签，获取的时候也一样
                    html会改变元素里面的内容，而且也会改变标签，获取的时候也是一样能获取标签
            */
        })
    </script>
</head>
<body>
<div id="a">
    <p>
        Yo.
    </p>
</div>
</body>
</html>
```
##### text和html的区别


![upload successful](\images\pasted-35.png)


# 增删元素


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
            //增加一个元素在后面
            // $("#a").append("<span>appendSpan</span>");
            //增加一个元素在前面
            // $("#a").prepend("<div>prependDiv</div>");
            //删除一个元素
            // $("#a").remove();
            //删除一个元素中的子元素
            // $("#a span").remove();
        })
    </script>
</head>
<body>
<div id="a">
    <p>Yo.</p>
</div>
</body>
</html>
```

# jQuery 事件

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        #card {
            display: none;
            background: #eee;
            padding: 20px;
            margin: 10px 0;
        }

        #card.active {
            background: #555;
            color: #fff;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            var card = $("#card");
            var cardTrigger = $("#card-trigger");

            cardTrigger.on("click", function () {

                if (card.is(":visible")) { //查看是否是显示状态
                    card.hide();
                } else {
                    card.show();
                }
            })

            card.on("mouseenter", function () {    //设置鼠标移入
                card.addClass("active");
            })
            card.on("mouseleave", function () {       //设置鼠标移出
                card.removeClass("active");
            })


        })
    </script>
</head>
<body>
<button id="card-trigger">
    显示/隐藏
</button>
<div id="card">
    <h1>公告</h1>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus alias distinctio dolorem enim facere, itaque
    nostrum reiciendis rem sit voluptatem. Culpa d olore excepturi fuga nam numquam quaerat quia tenetur ut.

</div>
</body>
</html>
```
#### 详细事件用法地址:[点击跳转](https://developer.mozilla.org/zh-CN/docs/Web/Events#%E8%A7%A6%E6%91%B8%E4%BA%8B%E4%BB%B6)

