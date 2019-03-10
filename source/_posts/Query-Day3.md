title: jQuery-Day3
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-02-20 18:28:00
toc: true

---
### jQuery中文文档址:
http://jquery.cuishifeng.cn/

# jQuery-内容选择器

#### :empty
	```javascript
   语法:var $div = $("div:empty");
   作用:找到既没有文本内容也没有子元素的指定元素
   ```
   
#### :parent
```javascript
 语法:var $div = $("div:parent");
   作用:找到有文本内容或有子元素的指定元素

```

#### :contains(text)

```javascript
 语法:var $div = $("div:contains('我是div')");
   作用:找到包含指定文本内容的指定元素
```

#### :has(selector)
```javascript
 语法:var $div = $("div:has('span')");
   作用:找到包含指定子元素的指定元素
```
# 属性和属性节点

#### 1.什么是属性

对象身上保存的变量就是属性

```
var p = new Person();
p.name = "Yam";//这个就是属性

```

#### 2.如何操作属性

##### 第一种方式
>对象.属性名称 = 值;
>对象.属性名称;   //获取方式

```
var p = new Person();
p.name = "Yam";//这个就是属性
console.log(p.name)//查看 

```

##### 第二种方式
>对象["属性名称"] = 值;
>对象["属性名称"]  //获取方式

```
var p = new Person();
p["name"] = "Yam";
console.log(p["name"]);

```

#### 3.什么是属性节点
```html
<span name = "it0114"></div>
```

 - 在编写HTML代码时 添加到标签中添加的属性就是属性节点
 - 在浏览器中找到span这个DOM元素之后，展开看到的都是属性，在attributes属性中保持的所有内容都是属性节点
 
![upload successful](\images\pasted-23.png)
  


#### 4.如何操作属性节点

>DOM元素.setAttribute("属性名称","值");//设置属性节点
>DOM元素.setAttribute("属性名称");//查看属性节点


```javascript
var span = document.getElementsTabName("span")[0];
span.setAtteibute("name","Yam");//设置属性节点的值
console.log(span.setAtteibute("name")) //查看属性节点的值

```

#### 5.属性和属性节点有什么区别

- 任何对象都有属性，只有DOM对象才有属性节点
