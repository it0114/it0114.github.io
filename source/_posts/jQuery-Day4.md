title: jQuery-Day4
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-02-21 20:15:00
---
# jQuery操作属性

#### 1.attr(name|pro|key.val|fn)
>作用:获取或者设置属性节点的值


>传参:可以传递一个参数，也可以传递两个参数
    如果传递一个参数，代表获取属性节点的值
    如果传递两个参数，代表设置属性节点的值

```javascript
	//    格式
		//获取span的class属性
		$("span").attr("class");
		//改变span的class属性的值，改为box
		$("span").attr("class","box");
		//新增一个属性
		$("span").attr("abc","123")
        
		<body>
		<span class="span1" name = "it0114"></span>
		<span class="span2" name = "Yam"></span>
		</body>
```
>注意点:
	-如果是获取:无论找到多少个元素，都只会返回第一个元素指定的属性节点的值
	-如果是设置:那么找到多少个元素，就会设置多少个元素
	-如果是设置:如果设置的属性节点不存在，那么系统会新增
    
#### removeAttr(name)
>作用:删除属性节点



>传参:属性节点名称

```javascript
//删除属性节点
	$("span").removeAttr("class")
        
		<body>
		<span class="span1" name = "it0114"></span>
		<span class="span2" name = "Yam"></span>
		</body>
```
>注意点:
他可以传两个参数，意思就是删除多个节点，但是得用空格隔开 例如 `$("span").removeAttr("class name");`

#### prop
>作用:获取或者设置属性节点的值


>传参:可以传递一个参数，也可以传递两个参数
    如果传递一个参数，代表获取属性节点的值
    如果传递两个参数，代表设置属性节点的值
```javascript
	//    格式
		//获取span的dome属性
		$("span").prop("dome");
		//改变span的class属性的值，改为box
		$("span").prop("dome","it0114");
        
		<body>
		<span class="span1" name = "it0114"></span>
		<span class="span2" name = "Yam"></span>
		</body>
```
>注意点:
	-如果是获取:无论找到多少个元素，都只会返回第一个元素指定的属性节点的值
	-如果是设置:那么找到多少个元素，就会设置多少个元素
	-如果是设置:如果设置的属性节点不存在，那么系统会新增

#### removeProp(name)
>作用:删除属性节点



>传参:属性节点名称

```javascript
//删除属性节点
	$("span").removeProp("class")
        
		<body>
		<span class="span1" name = "it0114"></span>
		<span class="span2" name = "Yam"></span>
		</body>
```
>注意点:
他可以传两个参数，意思就是删除多个节点，但是得用空格隔开 例如 `$("span").removeProp("class name");`

#### 开发中到底使用Attr还是Prop

>官方推荐在操作属性节点是，具有true和false两个属性的属性节点，如`checked`,`selected`或者`disabled`使用prop(),其他的使用attr();

#### attr和prop小案例
地址:https://github.com/it0114/jQuery-/blob/master/prop%E5%92%8Cattr%E7%BB%83%E4%B9%A0.html
