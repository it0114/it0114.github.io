title: Hexo-Admin插件
author: Yam
tags:
  - git
  - Hexo
  - 插件
categories:
  - 学习
toc: true
date: 2019-02-19 19:16:00
---


# 背景

>hexo+github搭建的网站，好处简直太多，但是坏处也不少，例如没有后台，这就是一个大毛病了，导致了没错写文章都要打开命令行执行`hexo n "文章名称" `生成一个.md文件之后还要去用第三方软件打开编辑保存调试最后再`hexo clean && hexo g -d `才可以把文章发布上去，这样的一套流程下来，简直不要太麻烦了好吗，所以现在引出了这个插件`hexo-admin` 

# hexo-admin安装

>- 插件官网：https://jaredforsyth.com/hexo-admin/

>在Blog根目录（注意:是Blog根目录，不是主题的目录）右键打开`git Bach Here`执行下方命令

```
 npm install --save hexo-admin
 hexo server -d
```

>执行完毕后打开 http://localhost:4000/admin/  你就会看到一个下面的图片

![界面](\images\pasted-0.png)

> 到了这一步 基本算了安装完了 你可以去使用 完全没有任何问题的 但是这并不是hexo-admin的核心

![皮一下](\images\pasted-1.png)

# 设置账号密码
>这是一个后台，这个后台我们当然不会想给别人能登录，能乱发文章乱修改，所以我们需要账户密码点击这个位置进行设置

![点击这个位置](\images\pasted-2.png)

>然后我们会进到这样子的一个界面，我知道你看不懂 ，所以我给出了一张图

![upload successful](\images\pasted-3.png)

>什么都别问，什么都别说，按照我说的做，最后点击`Setup authentification here.`

![upload successful](\images\pasted-4.png)

>还是什么都别说，也别问，按照我说的做，现在你应该复制好了，现在要做的就是把复制好的东西放到` _config.yml`，对，就是blog根目录里面的哪个配置文件，我怕你找不到，所以我又截了图

![配置图](\images\pasted-5.png)


----------


>打开这个文件 ，这个还要我说吗？


![配置图](\images\pasted-6.png)

>好了，填写好了之后，你可以刷新一下你的 http://localhost:4000/admin/ 这个界面，你会发现惊喜

![upload successful](\images\pasted-7.png)

# 写文章

>是不是出现了上面的情况 ，没关系，我相信你懂的，现在是写上你刚才弄的账号和密码，最后又会变回你熟悉的第一界面了

![upload successful](\images\pasted-8.png)

>是不是成这样子了，你现在可以试试按`New Post`写一篇文章，写好之后按右上角的`Publish`然后再去刷新你的` http://localhost:4000 `试试看行不行，如果不行，那么请认真看看文章，如果可以的话，那我们继续下一步

----------

# 设置一键发布 - 部署hexo-admin

>我们现在就算是写好文章，也只是在本地看得到，如果想在服务器看得到还是得在git执行`hexo clean &&  hexo g -d`，是不是觉得很麻烦？ 是的，我也这么觉得的，所以现在还得配置他，让他可以一键发布，跟我做

![upload successful](\images\pasted-9.png)

>点击他，你会发现出现了一个不知道是什么鬼的界面

![upload successful](\images\pasted-10.png)

>他会是这个样子的，现在我们要实现的功能就是点击`Deploy`就能把文章发到服务器上去。
 - 先在blog根目录打开`git Bash ` 输入下面的命令
 
 ```
 touch hexo-deploy.sh
 vim hexo-deploy.sh
 
 ```
 >会进图vim的输入界面 ，如果你不会怎么用，你可以上网上找一下简单的vim命令
 
 --------
 
 
 >在这里，你只需要把下面的代码黏贴到里面就好了 
 
 ```
hexo clean
hexo g -d
hexo s

 ```
 
 >都填写好了吧，还记得上面我说下面会说的哪个代码吗：`deployCommand`,现在再次打开配置文件，admin最后的位置添加` deployCommand: 'sh hexo-deploy.sh' `像下图一样
 
![upload successful](\images\pasted-11.png)

>再在根目录开git输入`chmod +x hexo-deploy.sh`修改sh文件的执行权限



>现在可以重新打开一下 http://localhost:4000/admin/ ，点击`Deploy`然后点击按钮，嘿嘿嘿，又有惊喜，你会发现下面的错误

![upload successful](\images\pasted-12.png)

----------

![upload successful](\images\pasted-13.png)

----------

![upload successful](\images\pasted-14.png)

----------
# 解决部署hexo-admin报错
>对的，你肯定会发现上面的错误的其中一种，真的很折磨的好不好，所以，现在我劝你可以参考一下
[github/hexo-admin/issues](https://github.com/jaredly/hexo-admin/issues/94),如果你看懂了，并且解决了，那当然是最好的，如果看不懂，那么还是看我的吧

----------

>打开`deploy.js`(blog根目录\node_modules\hexo-admin\deploy.js)，将`var proc = spawn(command, [message], {detached: true});`更改为`var proc = spawn((process.platform === "win32" ? "hexo.cmd" : "hexo"), ['d', '-g','clean','s']);`下面是改好的代码，你觉得麻烦，可以直接复制放上去


![upload successful](\images\pasted-16.png)

```javascript

module.exports = function (command, message, done) {
    done = once(done);
    //改这一行而已
    var proc = spawn((process.platform === "win32" ? "hexo.cmd" : "hexo"), ['d', '-g','clean','s']);
    //emmmmmm
    var stdout = '';
    var stderr = '';
    proc.stdout.on('data', function(data){stdout += data.toString()})
    proc.stderr.on('data', function(data){stderr += data.toString()})
    proc.on('error', function(err) {
        done(err, {stdout: stdout, stderr: stderr});
    });
    proc.on('close', function () {
        done(null, {stdout: stdout, stderr: stderr});
    });
}

```

>现在你再重新试试 打开http://localhost:4000/admin 点击`Deploy`试一下吧，你会发现下面的效果的


![图片](\images\pasted-17.png)

> 你现在可以试试写文章，部署，上传了， 嘿嘿嘿，简单的很;

# 结尾

>其实对于这些报错的解决方法有很多的，例如使用`.bat`批处理文件，例如直接在`deployCommand`后面填写代码，像下面一样![图片](\images\pasted-18.png)
只要有心，办法总比困难多的多，共勉



>对了，忘了说了，这个文章也是用这个方法写的。嘿嘿嘿

![图片](\images\pasted-19.png)

>这个就是界面，左边编写，右边查看，还实时可以在http://localhost:4000 查看，还是蛮不错的。唔...标签什么的那些东西的话在右上角的齿轮哪里设置，还挺好用的

![图片](\images\pasted-20.png)

> 元宵快乐


![图片](\images\pasted-21.png)

![元宵快乐](\images\pasted-22.png)