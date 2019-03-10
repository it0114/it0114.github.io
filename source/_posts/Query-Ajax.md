title: jQuery-Ajax
toc: true
author: Yam
tags:
  - jQuery
  - Ajax
categories:
  - 学习
date: 2019-03-03 14:14:00
---
# ajax方法
```javascript
		<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            // $.ajax("http://api.github.com/users/it0114")  //请求github
            //     .done(function(data){
            //         console.log(data);
            //     })

            var form = $("#search");
            var input = $("input#username");
            var result = $("#result");
            var username;

            form.on("submit", function (event) {
                event.preventDefault();  //终止浏览器默认请求
                username = input.val();
                $.ajax("https://api.github.com/users/" + username).done(function (data) {
                    var html =
                        "<div>用户名:" + data.login + "</div>" +
                        "<div>介绍:" + (data.bio || "无") + "</div>" +
                        "<div>博客:" + data.blog + "</div>" +
                        "<div>github地址:" + data.html_url + "</div>" +
                        "<div>url:" + data.url + "</div>"
                    console.log(data);
                    result.html(html);
                })


            })


        })
    </script>
</head>
<body>
<form id="search">
    <input id="username" type="search">
    <button type="submit"> 搜索github用户</button>
</form>
<div id="result">
</div>
</body>
</html>
```

