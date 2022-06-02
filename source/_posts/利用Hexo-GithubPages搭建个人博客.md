---
title: 利用Hexo+GithubPages搭建个人博客
date: 2022-06-02 22:14:18
tags:Hexo
---

## 一、 准备工作

1. 本地Git环境配置
2. 本地NodeJs环境搭建
3. GitHub个人账号

## 二、 安装Hexo并在本地初始化第一个博客系统

1. 安装Hexo

   ```javascript
   npm i -g hexo-cli
   ```

2. 初始化一个项目 <u>szl</u>

   ```javascript
   hexo init szl
   cd szl
   npm i
   ```

3. 本地启动

   ```javascript
   hexo g
   hexo s
   ```

4. 访问本地项目网站

   浏览器访问http://localhost:4000,初始化页面如下

   ![e9b57cc05b7f3ca263ea41ae8cfd0642](C:/Users/%E7%9B%9B%E9%95%87%E6%A2%81/AppData/Local/Temp/utools.notes/e9b57cc05b7f3ca263ea41ae8cfd0642.png)

   三、 创建仓库

![a273d87bc7cc2f998c2ab1580de6bb51](C:/Users/%E7%9B%9B%E9%95%87%E6%A2%81/AppData/Local/Temp/utools.notes/a273d87bc7cc2f998c2ab1580de6bb51.png)

![e2e79ab9361d33108ddb9302cb36a76d](C:/Users/%E7%9B%9B%E9%95%87%E6%A2%81/AppData/Local/Temp/utools.notes/e2e79ab9361d33108ddb9302cb36a76d.png)按提示创建好仓库

## 四、本地与github的链接

1. 配置文件_config.yml

   ![a9dd438899526fe4841e54d8a9475e69](C:/Users/%E7%9B%9B%E9%95%87%E6%A2%81/AppData/Local/Temp/utools.notes/a9dd438899526fe4841e54d8a9475e69.png)

   repo在此

   ![250e2c243e16f9a04c29f68a127839b6](C:/Users/%E7%9B%9B%E9%95%87%E6%A2%81/AppData/Local/Temp/utools.notes/250e2c243e16f9a04c29f68a127839b6.png)

2. 本地目录命令行

```javascript
npm i hexo-deployer-git -save // 安装部署工具便于以后更新博客

git init //本地仓库初始化
git remote add origin https://github.com/szl156/szl.github.io.git
```

```javascript
hexo clean && hexo g && hexo d // 更新到githubpage操作
```

 远程提交步骤

```
git status
git add .
git commit -m "First commit"
```

这里建议推送的时候创建一个新的分支用于管理hexo文件，提交的的时候只提交hexo网站html、css、等源文件而默认的master用来部署更新项目

```
git checkout -b hexo
git push origin hexo
```

## 五、githubpages配置

![17c6c45abd618622db1ae79df9196b56](C:/Users/%E7%9B%9B%E9%95%87%E6%A2%81/AppData/Local/Temp/utools.notes/17c6c45abd618622db1ae79df9196b56.png)

<br/>

***

# 可选内容：

## 更换主题

 由于Hexo官方提供的默认主题一言难尽，官方也特别人性的提供了上百种主题供您选择，[官网主题](https://hexo.io/themes/)点此前往，除了官方提供的主题外，还有许多民间大神的主题在github上，可供各位选择，本文主要介绍一款主题[pure](https://github.com/cofess/hexo-theme-pure)

### 安装主题

```
git clone https://github.com/cofess/hexo-theme-pure.git themes/pure
```

### 更新主题

```
cd themes/pure
git pull
```

### 启用pure主题

打开Hexo网站配置文件_config.yml，找到theme字段，将其值更改为pure

```
theme: pure
```

到此，主题安装完成。启动Hexo服务，检验主题是否正确启用。打开终端

```
hexo s
```

### 效果展示

不出意外的话，项目启动后应该是这样的

![94e224b86c8d68d4adbc319d0ba605a3](C:/Users/%E7%9B%9B%E9%95%87%E6%A2%81/AppData/Local/Temp/utools.notes/94e224b86c8d68d4adbc319d0ba605a3.png)

更多精彩配置，敬请阅读[官方文档](https://github.com/cofess/hexo-theme-pure/blob/master/README.cn.md)进行配置
