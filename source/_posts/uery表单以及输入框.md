title: jQuery表单以及输入框
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-03 00:24:00
---
# 表单以及输入框
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

            //获取input的值
            //  var nickname = $("#nickname").val();
            //  console.log(nickname);

            //设置input的值
            //  var nickname = $("#nickname").val("Yo")

            //直接选中input
            //  $("#nickname").focus();

            //全选input
            // $("#nickname").select();

            //取消激活input
            //  $("#nickname").blur();

            //如果是想监听事件 那么直接在上述的方法中传参function();
            // $("#nickname").focus(function(){
            //     console.log("Yam");
            // })


        })
    </script>
</head>
<body>
<input type="text" id="nickname" value="Yam">
</body>
</html>
```