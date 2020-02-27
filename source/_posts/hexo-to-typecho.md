---
title: Hexo小记以及四年总结
date: 2018-06-06 15:10:47
tags: 
    - typecho
categories:
    - 文章
cover: http://cdn.nenu.site/1839.png
---

# 挖了很久的坑

![tianhei](http://cdn.nenu.site/1839.png)
我是从2014年开始正式更新blog，四年下来大约积攒了百余篇。从一七年年底到今日，我访问自己的blog页面次数不超过十次，拖更自然是家常便饭。并非因为懒，而是无从下笔。四年（最早可回溯11年）过去，我点击自己博客下的两排友链，近乎八成已经归西。我不认为「[网络日志](https://baike.baidu.com/item/%E5%8D%9A%E5%AE%A2/124?fromtitle=%E7%BD%91%E7%BB%9C%E6%97%A5%E5%BF%97&fromid=87941&fr=aladdin)」这种方式正在没落，只是许多人坚持写作，特别是长写作的欲望和能力在减弱。我可以明显感觉到，网络与科技让人们在精神上更繁忙（某种程度上是这样的），举个例子，能把手机关机，静下心读一整天书的人几乎没有。为什么？你忍不住看，去刷空间，去获取一点点“可怜的”知识，美名其曰“碎片化阅读”；纵使你意志坚定，能够拒绝诱惑，也难免被微信、QQ等一众软件缠住。所以，能读好书的人在减少，能写文章的人也在减少，满足于微博，空间等短文字的人成了主流。

我喜欢这种形式，因为我可以掌控一切元素。这里是安静的，如果我不分享给你看，你甚至永远不会看到这些文字。我可以长篇大论，也可以尽情抒发“QQ空间式”的想法。总之，这些文字是孤独的，我从一开始就没打算为谁而写，自然不必考虑我的读者的感受，这也是我能坚持到现在的原因之一。

忘记说上面那副图，是我的第一个有名字的blog，由[typecho](http://typecho.org)强力驱动(其实现在还沉迷其中，前不久诈尸级更新，强力推荐）。前不久我把数据库打包到本地，然后删除了它，在这里开启New Part。看着几百MB的数据，突然有种沉甸甸的感觉：原来这些数据，我写了四年吶！这种感觉，很难在朋友圈、空间里找到，我觉得那里面的文字和图片不是我的，它属于腾讯和我的好友们。

## 关于Hexo安装的一些笔记（可忽略）

一.安装Node.js、Git；

二.github创建仓库和两个分支master与hexo（默认）并使用git clone 拷贝仓库 ；

三.安装hexo和必要插件（分支应显示为hexo）

```node.js
npm install hexo-cli -g 

hexo init 

npm install 

npm install hexo-deployer-git --save 
```

四.配置SSH密钥

```
cd ~/.ssh   
ssh-keygen -t rsa -C “x@qq.com” //打自己的邮箱 ，默认生成ssh key在C:\Users\username.ssh文件夹中，复制 id_rsa.pub文件到 github->settings->SSH and GPG key->new ssh key 
ssh -T git@github.com  //测试是否设置成功
```

五.全局配置user.name和user.email

```
$ git config --global user.name "xxxxx"//用户名
$ git config --global user.email  "x@qq.com"//填写自己的邮箱
```

### 一些常用命令

```
hexo g -d  //部署

hexo g -s //本地查看

git add .、git commit -m “…”、git push origin hexo //提交网站相关的文件
hexo n "文章标题" //写文章，默认目录source_posts

```

### 新电脑使用（参考CrazyMilk）

当重装电脑之后，或者想在其他电脑上修改博客，可以使用下列步骤：

1. 使用git clone git@github.com:CrazyMilk/CrazyMilk.github.io.git拷贝仓库（默认分支为hexo）；
2. 在本地新拷贝的CrazyMilk.github.io文件夹下通过Git bash依次执行下列指令：npm install hexo、npm install、npm install hexo-deployer-git（记得，不需要hexo init这条指令）。